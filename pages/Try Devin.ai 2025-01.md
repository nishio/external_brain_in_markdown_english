---
title: "Try Devin.ai 2025-01"
---

Log of the process of trying [Devin.ai
    - I started [[Meeting to see Devin]].

It's getting long, so I cut it out.
    - [[Try Devin.ai 2024]]

OLD TITLE: Try Devin.ai
- It's been a long time, so I'll cut it off after a month and continue [[Try Devin.ai 2/1~.]]. I decided to write it in

2025-01-02
About Session Usage Limit
- > Devin went to sleep due to session usage limits.
- ![image](https://gyazo.com/244856dde84816c84ba02e100fbc76ac/thumb/1000)
- W seems to stop well past Limit.
- PS
    - > The description reads like per session, but the limit of ACUs that can be used since the last user statement (by [teramoto](https://note.com/teramotodaiki/n/n31cabbaa4726))
    - Oh, I see. I thought, "Oh, I wonder why some things are beyond me.
    - It says "since last interaction".

[Devin's Observation Diary Day 3｜Daiki Teramoto](https://note.com/teramotodaiki/n/n301138ca120a)
> [nishio](https://x.com/nishio/status/1874538757745258691) "Now, finally, I have come to the point of financial paralysis. While I accept it as the cost of living one step further into the future, the occasional moment of calm is frightening."
>  Ahhhh I can't hear you - (who used up a month's worth of tokens in a week and got a refill).
> [nishio](https://x.com/nishio/status/1874541410600554567) All kidding aside, it's hard to say what is proper money sense.
>  When I first charged $3,000 for ChatGPT, I felt it was "the equivalent of a technical book. When I started paying that every month, I felt that it was a tool to improve business efficiency.
>  That's what I now consider "a person" to Devin. It's still cheap to think of him as a person.


> [nishio](https://x.com/nishio/status/1874706890858623422) I had Devin make this for personal task management, and the document he wrote is quite interesting, so I separated the data part and published it.
>  [https://github.com/nishio/ai_project_manager](https://github.com/nishio/ai_project_manager)


The muddled task of translating all Japanese comments in the source code into English was performed.
- [https://github.com/takker99/scrapbox-userscript-std/pull/215](https://github.com/takker99/scrapbox-userscript-std/pull/215)
- It's a simple, repetitive process, so it might be suitable for Devin.
- ![image](https://gyazo.com/79e8d9ad1cb1dccb3d28a43a35150cb9/thumb/1000)
    - [https://github.com/takker99/scrapbox-userscript-std/pull/215/commits/0e6a2efb71eb119a9ff0dfb04f58069376aaeb99](https://github.com/takker99/scrapbox-userscript-std/pull/215/commits/0e6a2efb71eb119a9ff0dfb04f58069376aaeb99)
    - Japanese wordy comments are being converted into English solicitous comments.
        - It's not just a translation, it's like you understand the code and you're writing it.
        - Not so simple as "a simple task."


> [takahiroanno](https://x.com/takahiroanno/status/1874561444811022377) Looking at Devin, it seems that the maintenance of documentation/knowledge in natural language to increase the probability of AI being able to build, implement, certify, and test the environment as much as possible is now part of the framework. maintenance / knowledge maintenance is going to be a part of the framework now.
>  >teramotodaiki: Devin's Diary Day 3

[Daiki Teramoto, Day 4 of Devin's Diary of Observations,](https://note.com/teramotodaiki/n/n8bb553c9f6ce)
[Devin's Observation Diary Day 5｜Daiki Teramoto](https://note.com/teramotodaiki/n/naa84266c26b5)
[Devin's Observation Diary Day 6｜Daiki Teramoto](https://note.com/teramotodaiki/n/nda1cd14694c6)
[Daiki Teramoto, Day 7 of Devin's Diary of Observations,](https://note.com/teramotodaiki/n/n31cabbaa4726)

### Cost of standby or sleep
.
- I wonder if it would be possible to timebox the time the AI works. I don't want to have to stop and wait for instructions and be attentive to chat.
- I want to do something like, "Now the human is going to do one pomodoro and report back in 25 minutes," and then I can go about my business for 25 minutes.
    - Q: Are ACUs consumed while stopped waiting for instructions in the first place?
        - Indeed!<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
- After startup: 1.
    - 0.42 @ 5min
    - 0.46 @ 10min
    - 0.49 @ 15min
    - sleep
    - 0.51
    - nishio: wake up
    - Devin Yes, it is happening. We await your instructions.
    - 0.54
    - nishio: what are the respective costs when Devin is thinking and resting?
    - Devin: Sorry, I don't have access to detailed cost information myself, you can find ACU (Agent Compute Units) usage and detailed cost information on the Settings > Usage & Limits page.
    - 0.60
- About $10 for a light LLM call or a 5 minute wait.
- About 100~200 yen for VM startup
- Light exchanges consume almost no ACU, so it feels like the cost is for the real work of reading lots of files, writing lots of files, and coming up with a plan after all!
- If so, it might be better to stop waiting for policy review than to go in the wrong direction and end up discarding the whole thing or incurring review costs.


> [teramotodaiki](https://x.com/teramotodaiki/status/1875809541209911452) I'm so glad I was able to use Devin so heavily over the holiday season.
>  Just like when I first touched ChatGPT two years ago, I felt confident that the rules of the game would change.
>  Compared to others around me, I seem to be optimistic, and I'm not even frightened that "my job will be taken by AI," but I think my resolution there has improved a lot.

> [teramotodaiki](https://x.com/teramotodaiki/status/1875813852543390004) The H in HCI is Human, but I guess that definition is going to get fuzzy...
>  If all the LLMs behind the scenes are side by side, the UI is the only place where they can compete, so the importance of the UI will increase even more. But that UI is not necessarily for Humans...it's like chaos


2025-01-07
I got confused!" and went to AI and AI managed it with great care...
- ![image](https://gyazo.com/cbdc5b27e06b5abca66e6bf66dfeb92a/thumb/1000)
    - Let's tell them first that Monday's task is done.
- This is a task management system that I have been developing without writing a single line of code, not even a git clone.
    - [nishio/ai_project_manager](https://github.com/nishio/ai_project_manager)
    - Devin.ai is updating backlog.yaml while talking to me on Slack
    - The above image is a reply with its backlog.yaml in ChatGPT 4o
- I'm starting to wonder backwards how far I can go without writing a single line of code.
- I guess it's time to clone...
- On second thought.
    - We don't need to play the "how far can we go in implementing this without humans tinkering with the code" bind game here.
    - This should quickly put me at ease by putting me in a position where I can "leave task management in peace."

After a little tweaking, I got the task dependency graph to output, but it's not great.
- ![image](https://gyazo.com/39a9eea4b4bf706b51e3183108801b2a/thumb/1000)
- Well, this doesn't look great, but the fact that the data (YAML) of the tasks created and organized by the AI while chatting with the AI can be visualized like this means that it is a decent format to generate.
- I was even able to generate stickies and arrows with [[Miro API]], so in the future I'll output to Miro instead of Graphviz.

the work of man
- ![image](https://gyazo.com/6d0f14d43a8c6053648832e4e995b1d4/thumb/1000)

Impressions at this time
- Because ChatGPT and other tools have been used by individuals, we tend to imagine their use, but this is designed to be used by a full-fledged team.
- Put it in Slack and communicate with it so you can see what others are developing with Devin.
    - Devin screens, work and thoughts can be viewed synchronously or retrospectively asynchronously later
    - In other words, this turns "individual work" into "pair-professional work with AI (humans are navigators)".
    - And the process is logged, so it's easier to make improvements.

Whether it's easy to see or not, they've created a script to visualize it in Miro.
- ![image](https://gyazo.com/2442808eff0a8c2703a3183220200899/thumb/1000)
- [https://github.com/nishio/ai_project_manager/pull/24](https://github.com/nishio/ai_project_manager/pull/24)
- Miro, so of course it can be moved and organized.
- If we can reuse stickies without changing their position when there are already stickies with the same ID, we can update them while preserving the ones that humans have rearranged.
    - Well, I tried the visualization by Miro API because I will use it for many things in the future, but it is not important regarding task management.
- Organized by hand.
    - ![image](https://gyazo.com/2c1e10d9851e37d4818f94508d37f388/thumb/1000)
    - When is Miro going to fix this "problem that sometimes the characters are too small in Japanese"?
        - <img src='https://scrapbox.io/api/pages/nishio-en/GPT/icon' alt='GPT.icon' height="19.5"/>Checking the Miro forum and release notes, there is some communication that they are aware of the Japanese display issue, but no specific fix schedule is available.
        - ouch!<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>

I told Devin, "Make a bullet editor that can be co-edited by AI and humans," and left it alone, and he made something.
- ![image](https://gyazo.com/650fda10ee39c4a59cc0fe35d1dfe9f3/thumb/1000)
    - Icons are very nice! Color schemes are great too!
    - What is co-editing or bullet-pointing!

[[Roo-Cline]]

> [teramotodaiki](https://x.com/teramotodaiki/status/1876674008210637130) Devin, Knowledge is useless when you're running multiple projects with different development policies.
> [teramotodaiki](https://x.com/teramotodaiki/status/1876674990265032900) Knowledge is all parallel, so writing something like "This is repository-specific knowledge" doesn't make much sense. It's just a reference to another repository's rules.
> [nishio](https://x.com/nishio/status/1876674757124641095) I think it would be easier to write it in the documentation of each project and have it read.
> [teramotodaiki](https://x.com/teramotodaiki/status/1876675401688494473) Maybe it would be better to put only meta content in Knowledge, like "keep all information in the repository", "be ready to take over the session at any time".... Maybe it would be better to put only meta content that is related to the nature of Devin, like "keep all information in the repository", "be ready to take over the session at any time", etc...?
> [nishio](https://x.com/nishio/status/1876675664734265460) "Don't commit your access token or private key to the repository"!
> [whitphx_en](https://x.com/whitphx_ja/status/1876676983536644604) Can't I just Pin to Repository?
> [teramotodaiki](https://x.com/teramotodaiki/status/1876677383941681178) I didn't know there was such a thing! I'll give it a try.
>  ![image](https://gyazo.com/6a326a70102c5d7bf8ec8d091d85c1ba/thumb/1000)
> [nishio](https://x.com/nishio/status/1876681551418941597) Gathering Knowledge!

[Devin's Diary of Observations Day 8｜Daiki Teramoto](https://note.com/teramotodaiki/n/n0c975f3928a2)

> [teramotodaiki](https://x.com/teramotodaiki/status/1876825690282086600) While the TL is all excited about DeepSeek-V3+Cline, our Devin just now service the Firebase project. He destroyed everything by deploying to a different app with the wrong account. Cute.
> [teramotodaiki](https://x.com/teramotodaiki/status/1876827111853281351) It's bad enough that I'm calmly being charged $1,750 in salary for destroying the development environment, but I'm getting used to it now. I'm going to step on all the landmines I can step on while I still can! I'm going to step on all the mines I can!


[Daiki Teramoto, Day 9 of Devin's Diary of Observations](https://note.com/teramotodaiki/n/n9340513acf56?sub_rt=share_pb)
> [akiroom](https://x.com/akiroom/status/1877031060225003553) The spirit was super excited and accelerated by the trial and error with the autonomous AI agent planning its execution and ordering food. I hadn't had a drink today since March 2023, when GPT-4 was released during the Language Processing Conference and we had a hot night in Okinawa.
> [Devin's Observational Diary Day 9｜Daiki Teramoto](https://note.com/teramotodaiki/n/n9340513acf56?sub_rt=share_pb)
> [akiroom](https://x.com/akiroom/status/1877031275610993043) I had thought of Devin as little more than an app development agent, but I was deeply impressed that it is now a general-purpose autonomous AI agent itself!
> [akiroom](https://x.com/akiroom/status/1877045326307041715) I wrote down some miscellaneous thoughts on Devin before I was shocked by it today at a drinking party. In fact, I had been spending $500 (75,000 yen) a month out of pocket since New Year's to actually touch the mess.
- [/akiroom/Devin Comments (until January 8, 2025)](https://scrapbox.io/akiroom/Devin Comments (until January 8, 2025))


> [teramotodaiki](https://x.com/teramotodaiki/status/1877366940487840027) GAME START
>  Game Start
>  ![image](https://pbs.twimg.com/media/Gg2_SEiaMAMylnV?format=jpg&name=large#.png)
> [nishio](https://x.com/nishio/status/1877380235085111348) I think I'll play the game of making an MCP server for Cosense too (...)


> [hrjn](https://x.com/hrjn/status/1877531993048797410) devin That's handy...I'm totally capable of doing simple tasks.
>  It's expensive, but...
> [hrjn](https://x.com/hrjn/status/1877532687432327252) But I wonder if a cursor composer agent would work with this level of dog. I think it is possible, but I wonder if it is easier to use slack.
> [nishio](https://x.com/nishio/status/1877537961819971693) For companies already using Slack, the utility of "human AI conversing with AI to visualize the status of each task" rather than "one-on-one black box between human and AI The utility of the "human AI conversing with AI to visualize the status of each task" is likely to be significant. It would be especially good for new hires and remote workers.
> [hrjn](https://x.com/hrjn/status/1877638015436394784) I haven't touched it much yet, but so far it's easier to use a cursor or other composer agent because it responds faster.
>  devin seems to have confirmed that it works, so that may be an advantage, but what I'm asking is too easy at the moment to realize the difference.
>  I think visualization of task status may be true, but I don't think it would be any different for humans if we made PRs with WIP and told them to push them.



> [nishio](https://x.com/nishio/status/1877568149735756225) To test "development processes" such as the "newcomer onboarding process", a "system that uses humans as components", a scarce resource that until now "newcomers without knowledge" was needed, but now Devin can emulate a human and thus increase the speed of system improvement. This kind of pattern of productivity improvement is also interesting
> [nishio](https://x.com/nishio/status/1877568598081765605) To abstract it one step further, it is a situation where "a human emulator can be used to test improvements to a system of which the human is a component, and the human emulator has all work steps recorded and its thoughts visualized. The human emulator records every step of the work and visualizes what the emulator is thinking. This is quite interesting, depending on how you use it.
> [nishio](https://x.com/nishio/status/1877570427381494249) Another interesting pattern is to use the human part of the "MVP with humans behind it" as Devin for user testing. By running it with messy and vague instructions and "actually using it", what needs to be clarified is identified. The cost to proceed to the phase of observing user behavior is reduced and it becomes easier to proceed in a lean manner.


2025-01-13

1/12
> [nishio](https://x.com/nishio/status/1878314610673291446) "Would you let an AI do your programming so you can make money without having to work?"
>  "If a system that makes money without the need for humans were realized, everyone would do it, so the resources needed to do it would be strained and prices would rise to 'unprofitable' levels."
>  I told him that.
> [nishio](https://x.com/nishio/status/1878314948738388031) So the only options are to get money in the transitional period leading up to equilibrium, or to get resources that are not money, or to do it in a domain where there are barriers to entry by the resources we already have. There isn't.



[https://github.com/nishio/contrast-game/blob/main/REPORT.md](https://github.com/nishio/contrast-game/blob/main/REPORT.md)
> We conducted an experiment to determine the extent to which an autonomous AI agent as of January 2025 can be implemented autonomously.
>  A game called "Contrast" was introduced at the 2025-01-10~12 programming symposium. While playing with the rules posted on the chat to have the AI review them for ambiguity and come up with effective strategies, the idea of having an autonomous AI agent implement this was born.
>  "Can AI complete a competitive server for a game discussed at Prosin during Prosin"? This was verified.
- The part that takes the most time is building the environment, so once you have something that works, it should be easy to just "build it based on this".
- Since AI can be tested by operating the browser, it is tempted to "test by operating the browser," and a considerable amount of real time is consumed in this process. It would be better to introduce a UI testing framework first, and to write what should be checked by operating the screen as test code instead of natural language.
- Insufficient understanding of the rules on the AI side became apparent when a UI was created and manipulated by a human, or when a test case was created. The human side was not aware of the inadequate understanding of the rules on the AI side while they were communicating in natural language. In cases with complex specifications such as this type of game, it would be better to first have a test case generated and then have a human carefully review it.

[Daiki Teramoto, Day 11 of Devin's Diary of Observations](https://note.com/teramotodaiki/n/n79eeca51259d)
[Devin's Observation Diary Day 12｜Daiki Teramoto](https://note.com/teramotodaiki/n/n8a8a7efec39f?sub_rt=share_pb)
> Give them a working template from the beginning, instead of making them create from scratch.
> Maintain testing and CI at an early stage to get the feedback loop going.
"I knew it!" feeling

I'm not talking about Devin, but I'm talking about a coding convention that might be suitable for AI to write code.
> [masuidrive [https://www.facebook.com/masuidrive/posts/pfbid023eH4BREcsXaK2oYXKwKLWg2T8fbtn8wVZxt8uoYYxfkejeSHpz9xbzcGxrDSDmzel?](https://www.facebook.com/masuidrive/posts/pfbid023eH4BREcsXaK2oYXKwKLWg2T8fbtn8wVZxt8uoYYxfkejeSHpz9xbzcGxrDSDmzel?) comment_id=1133444138160685] For example, when I have Sonnet write Python code, if I define an async method, I sometimes forget to await when I call it, so I write something like "The name of the async method must have _async at the end. So you should write something like, "The name of the asynchronous method must have _async at the end" to improve accuracy.
>  I've heard that the Hungarian notation for variable names would be better.

2025-01-13
# [[AI Agent Drinking Party]]
- Yesterday, I had a party for drinking AI Agents with the junior mentors who are using or making AI Agents, and based on what they showed me, I thought I should try [[Browser-use]] instead of trying only Devin.
- By doing Devin, I got to know "what will happen in the future when the parts are ready" and I can imagine a future where the contents of Devin will be o1 or o3!
- On the other hand, when I thought about whether I would enjoy my life as an "AI manager" or as an "engineer," I realized that I was still on the side of engineers.
- As an engineer, I want to drill down and understand the components that make up an AI agent, rather than abstracting AI agents as people-like
- Browser-use can also be activated with your own profile, so there's less hurdle when trying little things.
- 2025-01-16 What I thought after reading back.
    - > Devin gave me an idea of "what will happen in the future when the parts are ready" and I can imagine a future where the contents of Devin will be o1 or o3!
    - > On the other hand, when I thought about whether I would enjoy my life as an "AI manager" or as an "engineer," I realized that I still have some unfulfilled desires to be on the side of engineers.
        - This is "[[unintentional]]."
        - The nuance of truly believing that there is no future there and that it's not reasonable, but you can't stop yet.


> [teramotodaiki](https://x.com/teramotodaiki/status/1878461862481907814) I don't like boilerplate when I code, so I don't use it as much as possible, but maybe giving it to Devin will work better. I'm not sure if it would work better for Devin. This is the guy I need to unlearn.
> [nishio](https://x.com/nishio/status/1878802983590535467) Boilerplate is probably designed to allow less-skilled engineers to develop, and the current AI agents may be the equivalent of "less-skilled engineers. After a year, a new AI agent will say "I don't like boilerplate, can I rewrite it?


> [teramotodaiki](https://x.com/teramotodaiki/status/1878440307877945728) $500 a month is not even close to enough for this. Also, I guess I need a system to make sure I don't waste money to use it for a team.
>  "Yes, I spent 500 yen for that instruction.
> [nishio](https://x.com/nishio/status/1878803890868801935) I need a cost visualization feature, I've been trying to do a long list of futile things while being unresponsive in Slack...
>  I also thought that there would be a conflict between those who are for spending it without concern because it is company money and those who are more cautious than with their own money because it is company money.


> [ochyai](https://x.com/ochyai/status/1875507151944527951) The one that works for Devin: "Make sure you put out new pulls. If I can't do it right, I'll think about renewing my contract ..."

> [ochyai](https://x.com/ochyai/status/1879019923940552786) Devin's killer use is writing survey papers. I'm probably very good at this.
- However, they will halucinate and cite references that don't exist (there are some).

2025-01-14
> [nishio](https://x.com/nishio/status/1879152428106514892) Devin! I told you to listen before you run it! Why is the Pull Req coming!
>  ![image](https://gyazo.com/917273e9c3c1234e69b4ce147623f3fc/thumb/1000)

> [nishio](https://x.com/nishio/status/1879158636561473573) Devin, I only asked you to fix the documentation, but you cheerfully fixed the GitHub Action and requirements.txt as well, You're very good. "No testing is required since the change is only in the documentation.
>  ![image](https://gyazo.com/e65d7e98a75398d50e7a1d8e402a0d64/thumb/1000)

[Daiki Teramoto, Day 14 of Devin's Diary of Observations](https://note.com/teramotodaiki/n/nc88cb48a0b47?sub_rt=share_pb)
Performed w
> [nishio](https://x.com/nishio/status/1879157133889114438) Ah, I see, you thought you put it in the cart and pressed order, but because of the agent operating in parallel, a race condition occurred and it disappeared on its own, and you were scolded that "the order was not completed. I guess I got impatient because I was scolded saying "it's not done"... ()
> [ukkaripon](https://x.com/ukkaripon/status/1879160707633316163) due to the owner's power harassment prompt.
> [nishio](https://x.com/nishio/status/1879161506904059951) I knew that an AI with [[orchestration layer]] is human, so it shouldn't be power-hungry.

2025-01-15

I was running my own task management written by Devin with ChatGPT, and to my surprise, I found that there are two codes for validation, which one do you use?
(It's the fault of the person who merged without checking properly.)
I had o1 pro rewrite it wonderfully (...)
- (teramoto) If Devin were human, he would be pissed off.
    - (nishio) It's wonderful that you don't get mad at me for "hurting your pride" or whatever.

The one written by o1 pro worked fine and found 10 undetected mistakes (...)
You have duplicate IDs.


- 1: The inability of the current Devin to gather information across multiple threads of devins increases the human management burden.
- 2: It is difficult for people using via Slack to realize that Devin's performance decreases as the context gets longer, and it would be good if Devin itself had the ability to take over to an instance in a different context, saying "I'm tired, let's quit and continue in another thread.
- 3: The structure that makes it difficult for end users to be aware of the credits they have used will be a challenge to implement in organizations with a larger number of users. Currently, it is too much work for the system administrator to put Devin into the organization.
[[Scott Wu]] and shared the above
- [[Meeting with Scott Wu]]

> [chokudai](https://x.com/chokudai/status/1879478898934882702) Devin, who is starting to make a name for himself as an AI software engineer, actually seems to be making a lot of competing professionals.
>  There are tourist(AtCoderRating 1st place), ecnerwala(4th place), scott_wu(12th place) just visible in the introduction video, and the homepage says like 10 gold medals in the World Information Olympiad.
> [chokudai](https://x.com/chokudai/status/1879479464918413447) scott_wu, I saw you as the highest ranked competitive professional, but when I looked at Wikipedia, you are mainly treated as an entrepreneur. Heh.
I didn't know they were competitive professionals.


> [y_matsuwitter](https://x.com/y_matsuwitter/status/1880080844951572485) Devin, our new hire, is not good at big tasks, but he does a good job of speeding up deployment, replacing labels, fixing minor bugs, etc. He's been great. Today, he reduced container size. He has a knack for the granularity of tasks he is entrusted with.
> [y_matsuwitter](https://x.com/y_matsuwitter/status/1880169627793387662) Ai Workforce team-wise, he is already being treated as an excellent teacher that fits the cosponsor. He just can't handle big tasks, but he is excellent in terms of knowledge.
> [nishio](https://x.com/nishio/status/1880191358373392865) This "knack for granularity of delegation," "difficulty level of what can be done," "sense of cost that might be incurred," etc., is basically what we are experiencing for the first time, so "actually using it to gain experience" I think the only way to learn it is by doing it. No matter what textbook you buy, it doesn't say that.
- > [skyTrilingineer](https://x.com/skyTrilingineer/status/1880290535761670662) Seeing is believing, right?
    - Rather [[one eye-witness is better than many hearsays]] feeling

- > [takiuchi](https://x.com/takiuchi/status/1880303745915076740) The problem is that all those tips are not going to be useful when the AI generation changes.
    - > [nishio](https://x.com/nishio/status/1880422872314966295) This tweak is absolutely correct, but this exchange was about "What programming language should I learn? If the language changes, I can't use the old language as it is, right? Please tell me which language will be safe in the future if I learn it! I felt that this is the kind of thing that has been repeated in the past. There is no such thing as perpetual technology.
    - > [ringo](https://x.com/ringo/status/1880452602938421371) I guess I still don't know if this tweak is the right one.
    - > [nishio](https://x.com/nishio/status/1880453691901354472) I was short on words. I tried to be more precise by adding more words, but it sounds like "[[Superficial knowledge]] changes without [[compatibility]], [[deep understanding]] remains partly beneficial, [[it is impossible to know in advance which parts will remain beneficial]], [[you can't just skip the superficial knowledge and get a deep understanding. which parts will remain beneficial.]], [You can't just skip the superficial knowledge and get a deep understanding.
    - > [ringo](https://x.com/ringo/status/1880461280936620366) You can't make an AI sing the Doraemon song, or read a picture book, or anything political, weapons, dangerous devices, reverse engineering, personal human activity or contemplation. There are quite a few topics about which it is not useful in terms of safety.
    - >  In summary, everything that is not pretty.
    - > [ringo](https://x.com/ringo/status/1880461682067349965) It would be nice to be able to make an AI that thinks with us about things that aren't pretty for us with the computing power at our fingertips, but I don't think the prospects are there yet! [[ringo ]]

- > [fpocket](https://x.com/fpocket/status/1880403257417429167) The field of Process Automation has been recognized for its importance since the early 2000s, but there has not been much development of mathematical scientific methodologies. In particular, there is a lack of mathematical scientific methodologies for how to decompose tasks into processes. I look forward to seeing more development of sphere theory-based methodologies and representations, also related to Plurality.
    - I'm not sure if it's sphere theory based or not, but at least until a few years ago it was assumed that "task decomposition" was something humans do. It is now possible for machines to do it, and if anything, they do it better than humans in some situations. How to set up the situation to do it well is the subject of new engineering research.
        - > At least until a few years ago, it was assumed that "task decomposition" was done by humans. It is now possible for machines to do it, and if anything, they do it better than humans in some situations. How to do it well under the right circumstances is the subject of new engineering research, and whether or not sphere theory is a good idea is being tested experimentally.
        - I'm not sure if it's sphere theory, [[graph DB]], or [[structural programming]] at this point.


> [nishio](https://x.com/nishio/status/1880426068932444262) Yesterday, I talked about the "typical hype curve" where "people who tried Devin early on get excited about the fun of it and send out too much information, which is interpreted as 'just buy an expensive Devin and you'll be happy.' I talked about the "typical hype curve" where "people who tried Devin early on got excited about the fun of it and started sending out too many messages.
> [nishio](https://x.com/nishio/status/1880426444603682889) "Early adopters and the majority are misaligned on the axis of values" is a common story.
> [teramotodaiki](https://x.com/teramotodaiki/status/1880465589300560208) I think this is exactly right. Mr. Nishio and I melted tens of thousands of yen while laughing and saying, "That was fun! but still, sometimes, I suddenly come back to myself and feel depressed. If you don't want to regret it, I suggest you don't buy it yet.
>
>  I think this is about the only person who should sign up for Devin as an individual.
>  ・People who are willing to spend their own money to advance their company's use of AI.
>  ・Influencers who can collect $80,000
>  ・People who can separate the cost of study from the cost of learning about the future.
> [teramotodaiki](https://x.com/teramotodaiki/status/1880465590852436338) On the other hand, "Should I contract Devin at my company?" On the other hand, the answer is 100% YES. We should start thinking internally about how software development will change in the future. The bigger the company, the bigger the impact, so if I were working for a large company, I would call myself "Chief Devin" and promote it all over the place.

Mr. Nishio and I melted tens of thousands of yen and said, "That was fun! and laughing, but]
> [nishio](https://x.com/nishio/status/1880465589300560208) I don't think people really understand what I mean when I say "I'll pay for it and we can all observe together" instead of "I'll pay 80,000 yen and try it alone". I don't think people really understand the meaning of the move, which is to say, "I heard you can rent a cruiser for 80,000 yen! Let's all ride together! In fact, I had a lot of fun and had a lot of fun that I couldn't have experienced alone.
> [nishio](https://x.com/nishio/status/1880472581578567964) The "[[travel]]" metaphor is a good one. The "memories" and "experiences" stay, but they can disappear by the hundreds of thousands. And going alone and going together are fundamentally different experiences.

If I worked for a big company, I'd call myself "Chief Devin" and promote it all over the place.
> [nishio](https://x.com/nishio/status/1880471715714899968) I think the benefits of implementing Devin in a company are great, but I personally don't want to be the one to lead the implementation drive, persuade, negotiate, get the budget, adjust expectations, encourage those who don't use it, abus... I don't personally want to be the one to lead the implementation, persuading, negotiating, getting budget, adjusting expectations, encouraging people who don't want to use it, abusing them and making sure they don't have problems... It looks like the type of work I'm not good at and don't want to do.


I was going to increase the limit on tasks stopped by the session usage limit, but now I get a warning that it's not proper usage to be in that state in the first place.
![image](https://gyazo.com/539488f713b0d7dea0b28248fb7b664d/thumb/1000)
He evolved to be angry with us because we were using it in a rather strange way, and he said, "Don't use it like that and say it doesn't work well.
Well, I think this is one of the features you need if you are going to implement this in your company, because even if you have 250 ACUs, if you throw 100 ACU tasks at a shot before you get a feel for what tasks will take how long, you will lose them quickly.
It would be nice to have automatic feedback that "the limit was reached without completing even 1/10th of the expected task."

People who don't have a skin in the game of what to ask an AI assistant to do tend to ask for 'a lot of tasks' when they want to ask for something.
- But in practice, having N similar tasks that are not directly related to each other performed together has a non-linear cost and a large delay until the human verifies the results and learns from them.
- Even if you eventually want to do that N case, you need to repeat the experiment in small steps first to observe quickly what mistakes the AI makes and to know how to direct it to do what you want.
- In addition, when N is large, it is usually not reasonable to have N cases done at once, and it is necessary to break them up into reasonably cohesive chunks of tasks.


2025-01-19
Especially when it comes to task management, the interface is Slack, which has the advantage of "being able to instantly write down what comes to mind and get it out of my head.
- o1 is waiting too long.
- 4o is quick to react, so there's no human wait time, but it's strongly influenced by what you say, Devin can put it aside.


If Devin had been left to his own devices, he would have created a number of codes that do similar things.
- For a new person/AI, the balance point between looking around to see if there might be code for a similar purpose somewhere in the pile of code and writing new code is more on the "writing" side.
- It is through implicit understanding of the source code that humans are able to realize that they have already written something. It is not written anywhere in the documentation, etc., and we remember it in an undocumented form based on experience, such as "I must have created it as a component when I created that function.


I gave [[o1 Pro]] a bunch of documents and discussed if there were any questions, and a lot of things came up.
- So, after agreeing with them or answering their questions and giving them new information, I said, "Make it a specific task instruction.
- I threw the instructions that came out to [[Roo-Cline]].
- Devin's [[orchestration layer]] behavior probably looks like this
    - The more humans do it, the better we understand it.


I'm starting to feel the need to throw out a lot of "unused scripts" created by Devin and "documentation explaining how to use unused scripts".
    - [[Human Work: AI Ruthlessly Throws Away What It Writes]]


2025-01-20
Devin Incident
- Knowledge gained from a private repo is written in the PR of a public repo.
- It's not a catastrophe because we haven't put in anything fully fledged and top secret yet.

Today's task management experiment is a win for ChatGPT, a mistake that Devin says takes a woeful amount of time and causes a security incident.
- After all, at the moment, AI may be better confined to a private ORGANIZATION, rather than in a form that can be written in a public forum.
- That would make it a pain in the ass to commit directly to an open source project.

- (Tachibana)At first I thought it was the opposite of me just looking at the letters, but then I saw the <link> and understood.
    - I use Devin only for OSS now because I think public projects are more suitable for AI sandboxes because there is no sensitive information (I only give Devin information that can be used for OSS from the beginning), but we have the same view of security and different assumptions.

- (Teramoto)We are preparing rules for internal use, and we are going to ban public repositories uniformly. But the risk of writing something bad in the public repository is non-intuitive, isn't it? I can understand it when I hear the examples, but I think there will be more companies that will do something wrong.

Coupled with the fact that it was originally difficult to pass negative-type instructions to LLMs, it's difficult to instruct them not to leak information to the PUBLIC.
- So, if you've been operating under the "keep data in a private repo" policy, and you've been able to do that, but then you happen to write in a table, "I've put the organized documents in a PR!" I've been able to do that until now, but now I'm thinking that I have no choice but to write in private repo only if I write in the table. I have a feeling that this is a good idea.
- It's like even if the probability of doing something like this is small, the damage when confidential information is written in a public repo is so great that the expected value of multiplication is large.

I'm using Devin originally with the intention of sharing it, so I haven't put anything seriously confidential in it yet, and I'm making it a public repo because I think it's better for as many people as possible to have the opportunity to observe it, but I think it would be straightforward to make it private if we want to utilize it in the future...
- > "Public projects are the best suited for AI sandboxes because there is no confidential information."
- This is really true, because if there is no secret other than the string to be put in the secret, the risk of leakage is low (although something like the case of the leakage of half of Teramoto-san's private key may happen).
- I would like to rethink the design of Devin workspace and the operation of this place, considering various things like
- And in about a week, it'll be a month since we started.

(Teramoto)Well, it is difficult. I learned from Mr. Nishio's task management that it is not always the source code or secret that leaks, so I have to make the assumption that "everything Devin sees leaks" (...)
- But I can't let anything happen if I make such assumptions about the stones...
- > Learning that it is not always the source code or secret that leaks
    - Good summary<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>

2025-01-21

Toward the Closing of the Meeting to See Devin
To be done in the next week or so.
- Devin privatization
    - Reconnect Devin to Nishio's personal Slack.
    - Davin.ai Remove all but Nishio from WebUI members
    - Delete public repo from Devin workspace and make only private repo (because there is a case that repo is pushed by mistake).
    - If the AI task management system is "to be developed publicly" and "usefulness to Nishio", now is the phase where the latter should be pursued, so it was changed to "private repo all together".

Devin's new observation opportunity will be gone, but I'll consider it enough of a social contribution to have provided the opportunity to about 30 people for a month.


As an aside, I actually know the reason for yesterday's accident, and I think it was because I changed the way I placed the data and other things in the process of "experimenting with ChatGPT and Roo-Cline" from "working with Devin alone" to "experimenting with ChatGPT and Roo-Cline", which is why I got confused.
Well, I don't want the public repo to PR the contents cloned from the private repo because of the confusion...
Maybe it would have been better to fix the mechanics side of things instead of continuing at the stage where they were confused about reading test data and such.


2025-01-22
Creation in the form of scraping off what the AI has written, rather than writing
- [[Sculpture, not plasticine.]]
    - [[Minus design]]


AI task manager, ChatGPT has made it possible to have the output in jsonpatch format and APPLY, so the need for Devin to rewrite the file directly is becoming less and less necessary...
Thanks for the help in prototyping, Devin...

If you let Devin handle the code for the system that hits OpenAI's API and processes it, he'll also do the trial and error for the prompts. w
- [[Trial and error automation]].


My thoughts like "we should do it on the public channel for transparency" and my "I want to share with as many people as possible how Devin behaves" are not balanced by the smarts of the AI at this point in time.
It's more like "don't give public social networking accounts to kindergarteners".


[Summary of Devin's observation diary so far. Why is Devin "destructive"? |Daiki Teramoto](https://note.com/teramotodaiki/n/n349d1d361804)
> Cursor, Roo Cline... They are only tools in that they "constrain the user".
> Devin's characteristics need to be understood and the team needs to think about overall optimization.
> After all, letting them do their job = giving them discretion.


> [nishio](https://x.com/nishio/status/1881755732879737262) I let an AI decide when to sleep and it told me to wake up at 7am
> ![image](https://gyazo.com/3c8dbc92f67dce97ba9c96ff44453625/thumb/1000)
> [nishio](https://x.com/nishio/status/1881931754086486186) I complained and they extended it by 2 hours.
> [nishio](https://x.com/nishio/status/1881941555050901593) My Devin said, "Humans need enough sleep - I'll make a note of that."
>  ![image](https://gyazo.com/9708e2bd6ee38e8eebe4a6a6ea5e76ed/thumb/1000)


2025-01-24
![image](https://gyazo.com/2919f9e835117eae6cea24a8ea41368c/thumb/1000)

2025-01-25
- [[Closing of the meeting to see Devin]]

2025-01-28
- [[Scope of AI agent write]]

2025-01-31
- [[Have Devin do the code reading.]]
- [[How to Melt 40,000 in Devin]]

- [[AI Agents Bring Genrality]]

Since it's getting quite long here too [[Try Devin.ai 2/1~.]] I decided to write the rest of the article in

---
This page is auto-translated from [/nishio/Devin.aiを試す2025-01](https://scrapbox.io/nishio/Devin.aiを試す2025-01) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.