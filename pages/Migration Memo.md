---
title: "Migration Memo"
---

[[pKeicho]]
I want to put a Web UI on a chatbot built with CUI and connected to Mattermost.
It's all jumbled up and confusing, so I'm going to proceed as I write.

- The existing repository is a jumbled mess of various ties, so let's separate it into a new repository.
- `$ git init keicho-server`
    - Working with [Natural Language Processing on Heroku
    - `$ heroku create keicho`
        - It's obvious that putting it on Heroku is a server.
- Minimal code runs on the server.
    - This is where it gets tricky.
- Understand and organize past codes.
    - ![image](https://gyazo.com/b9ae8e5954c15ae5acd949fb026235af/thumb/1000)
    - In the CUI era, information was held on-memory.
    - Connecting Mattermost with Outgoing Webhooks
        - That's why I started putting the information into Firebase at the stage where I was trying to bring it to the server.
    - call `chat.connect_slack(username, text)` from server
        - I didn't package it then, but should I take this opportunity now?
    - environment.py takes care of defining the env object and persisting it in Firebase.
        - Ah, here's where putting credentials for access rights in the repository makes it harder to publish...
        - Then I thought, "If I separate the secret part of the repository, how can I attach them together in Heroku?
        - Keep the default private, and only cut out the parts that can be made public to a public repository.
- The import so far has worked fine.
    - Create a test URL for Firebase connection and try to hit it.
        - Calling state.py from environment.py
        - See INITIAL_STATE
        - I didn't want to make this too tightly coupled, so I split it into state_constant.py / state_action_map.py.
        - The persistence perimeter is now working.
- next
python

```
def connect_slack(name, text):
    "Top-level interface for chat server"
    env = environment.load(name)
    env.log.append([1, text])
    if text[0] in "!(>#~@":  # (1)
        environment.save(name, env)
        return ""

    process_command(env, text)  # (2)
    res = make_response(env)  # (3)
    if res:
        env.log.append([0, res])
    environment.save(name, env)
    return res
```

    - Not sure what (1) is needed for...
    - process_command
        - The first important thing is feedback when the question is "not a good one".
            - If it's NGKW, then the keyword choice itself is bad.
            - NG can't answer the question because the keywords themselves are not bad, but the combination with the question is not good enough.
            - It's not clear that humans can properly distinguish between the two, so if you use the latter two or three times, you may want to consider it a bad keyword.
        - The environment is being reset when the reset command is sent.
            - This is because in the case of chat, there is no "session" or anything like that, so there is no reset timing.
        - Normal flow is initiated by "let's talk" etc.
            - This also serves the purpose of waking up Heroku from sleep.
            - For the Web UI, input should be available when the page is accessed, and should happen in the background
        - Return to normal mode by "first listen" phase mode and "end" mode
        - Experimental code that drops the score with statements like, "Not really."
            - Feeling that should be done with NG command handling, etc.
            - Comment out once, review later
        - I'm outputting the logs in an easy-to-read format for later reading, but it's written in a local file because it's CUI era code.
            - I feel like I've added a log display function in the Slack era, so I guess it's a good thing I don't have it.
        - Storage of environment and response length data
            - This is the idea that "questions that get a lot of answers back are good questions".
        - env updates
            - later mention
        - Update data for question keywords vs.
            - The data for the study was spit out to a local file, commented out in the Slack days.
- Hmmm, I see.
    - ![image](https://gyazo.com/f8c2d6a5951c8eb8bfff9cc08807b89d/thumb/1000)
    - process_command is bloated because of its ambiguous, anything-goes function name, and it calls a function that could be anything, such as update_env.
    - Conversely, make_response has two lines (and one of them is assert).
    - This one doesn't have proper division boundaries, it's a labyrinth of repeated buildups.
        - Let's put them together and then divide them appropriately.
    - In update_env, there are more calls to state_transition.
        - I'm mainly working on state transitions here.
        - I'm logging state transitions, but still only on the local file system.
        - Shouldn't we have created a separate location in Firebase for the logs that are written to a file at the same time we rewrote the on-memory information to be persistent in Firebase? (to be discussed later).
    - liquidation
        - The part of process_command that really processes the string as a command wants to escape with return, so it is natural to split it into functions
        - The same goes for state_transition
        - ![image](https://gyazo.com/00bcda856bb76dab5bbd5af342a2e3e0/thumb/1000)
        - I was doing keyphrase extraction in update_env_with_input, too deep.
- keyphrase extraction
    - I'll leave the code as it was once in the past for now, but will be updating it soon, so I'll cut it out.
    - Key phrase extraction will be used in other projects, so let's package it.
- Delete key phrase in NGKW
    - Both with and without phrase specification are implemented, but they are never used with a phrase specification.
    - Here, I'm simply deleting it from my memory, but that doesn't leave any information that it was "deleted".
        - May be added again.
        - It should be blacklisted or otherwise not added during the session, and in the long run, it should be played on the blacklist during the keyphrase extraction portion (to be discussed later).
- While connecting to Mattermost has made it easier to use, it has also made it harder to improve by disabling various logs, I regret that.
- Next, around the action.
    - Designed to have an action for each state, which is executed with the env as an argument.
        - `state_action_map[env.state](env)`
    - But in practice, with a few exceptions, the action "choose from a list of questions received in the argument and ask a question".
        - I thought the selection was random, but it wasn't.
            - Calculate scores for all key phrases x questions
                - Exclude items that have already been mentioned or are on the NG list.
                    - I wonder where this NG list comes from...
                    - It's in the env persistence target, but when you stop exporting the NG list file, it also stops adding to the list, so it's always empty.
                - I'm clogging up the basic two questions.
                - There is a positive correction for the keywords used in the previous question.
                - There's an adjustment here to see if it's a natural question, but it hasn't been tested to see if it's working effectively.
                    - I think it's unverified, but did you verify it? I'm not sure.
                    - Remove it and consider later.
            - Then select the one with the largest score
                - put to use
                - For symmetric questions, the keywords exchanged are also included in the used category.
- question
    - For each type of question, "choose one key phrase", "choose two", etc. are implemented.
    - Some sampling based on score.
    - Huh? I thought you just calculated the scores for all the key phrase question pairs and chose the largest one.
    - Yes, this wasn't called for.
    - The exception, ChainQuestion, is "continue to use the previous keyword"...
        - I don't think this has been properly tested.
            - Maybe it just so happens that "the keyword with the highest score last time has a higher probability of being the highest next time," but it could be reversed.
            - They should be flagged as "questions that continue to use the immediately preceding keyword" and given special treatment when calculating scores.
    - Remove unused codes.

- It worked on the local server.
    - It worked on Heroku too.

We'll discuss it later.
- How about a way to fix the part or seed that is treated as random, so that we can test regression?
    - Randomness has already been removed to begin with.
    - Lack of fine granularity testing is not good.
- A: Logs that are exported to a file should also have a separate location in Firebase.
    - Yes
    - What logs should be kept?
        - Currently, the "human readable log" itself is also placed in the realm of being reset, which is odd.
        - At a minimum, logs should be kept for human reading
        - Plus, it would be nice to be able to look at the logs and see the internal data later when the "not-so-good response" was happening.
            - This is going to take a lot of capacity if we are not careful...
- B: In the long run, the blacklist should be played in the key phrase extraction section.
    - I don't have a place to keep track of this right now.
    - Do A first.
- C: Experimental code that drops the score with a statement like "nothing special".
    - Feeling that should be done with NG command handling, etc.
    - B and then put it together.
---
This page is auto-translated from [/nishio/移行メモ](https://scrapbox.io/nishio/移行メモ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.