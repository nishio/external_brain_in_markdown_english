---
title: "pKeichobot"
---

- Project note on [Listening Chat System

from [/villagepump/why-I-make-Wiki](https://scrapbox.io/villagepump/why-I-make-Wiki).
- Scrapbox→Keichobot
    - It would be nice to be able to have a "let's have a conversation based on what we've talked about so far" while writing Scrapbox, but if you want to run it on Scrapbox, you have to use browser extensions, etc.
    - Keichobot is designed to be used while walking around with a smartphone, so the choice of browser extensions is not great
    - I can take data on a page-by-page basis and use it as a reference (just noticed).


--- old memo 2021
2021-08-20  [[Renamed from Keicho to Keichobot]]

    - [[Sample of how to use Kikidashi Chat]]
    - [[Listening Chat System Conversation Log]]
    - [[Kikidashi Chat System Release Notes]]

Kanban in Scrapbox
- WIP
- HaveBetter
        - [[🤔Allow footer to be specified when exporting to Scrapbox]]
    - [[Dynalist]]
        - [[□Recapture screenshots of commentary]]
    - The Phenomenon of Separate Conversations
            - [[I'd like to discuss a bug that caused a mysterious log breakdown.]]
    - Make questions that do not take other keywords score in active learning.
        - What exactly?
        - Then [[End Design]].
            - [[I was talking about how active learning doesn't work, and I concluded that you should read books.]]
        - [[🤔Task Management Chatbot]]
        - [[🤔 screen height and virtual keyboard issues]]
    - Is local storage shared or not when "bring to home screen" in standalone?
    - [[🤔http would not work with clipboard? #606da96aaff09e0000d54778]]
        - [[Accept only 🤔choice answers]]
        - [[Put 🤔 mode changes on the menu?]]

[[pKeicho202103-202104done]]

Memo
    - [[End Design]]
    - In the derivation, "[Allow questions to create command buttons.
        - [[Conversation log 2021-01-30]]
        - I think the endgame of this one is probably that after the mode transitions to asking about relationships between symbols because it has a lot of keywords and considers them developed enough, it runs out of high scoring words, but it's still in the asking about relationships mode.
        - Perhaps judging it from the distribution of keyword scores,
        - I propose an end.
        - Propose a new chat.
        - Return to search mode
        - I think it would be appropriate to do one of the following
    - [[question naturalness data set]]
    - The amount of features should be improved.
    - Related: [[Tuning questions that take two arguments]].
        - Do not repeat symmetrical questions: done
        - Need to collect naturalness for questions that take two arguments as well.
    - Related: [[Good and bad feedback during conversation]].
        - NG feedback is used as training data
        - → Not enough data and poor quality as training data.
            - I think I'd be better off teaching through active learning.
- ---
    - [[One-click import to Regroup]]
    - [[IGNORE file to exclude inappropriate items from the analysis]]
    - (e.g., logs that are not being used properly)
    - [[Feedback button: Like]]
- Do not tamper with the score to represent the subject of interest.
    - This is causing confusion between "what is actually repeated in the user's statement" and "what the system determines to be noteworthy".
        - [[Score = development, not attention]]
    - [[If you were to create a task-organizing version of the listening chat system]]
- In response to the input "Tsu, Tsuyoshi".
    - Not selected as a keyword because "strong" is an adjective.
        - "What kind of "tough" is that "tough"?" is an ant question, so you might want to extract it.
    - The "つ" can be a noun, so it is included in the keywords.
    - The result is that you end up asking "one" digging question.
- Play keywords that are not good.
    - The CUI version had.
    - Turn it off when you make the Mattermost version and keep it off.
    - Use NGKW feedback to learn!
    - →There are quite a few cases where users are unaware of NGKW even though it's a good keyword, and learning from users makes you a fool.
        - I put it in the form of putting only the obvious no-no's on the list.
- What we want to feedback
    - Keyword extraction is not the first step.
        - > You're starting to buy into the subtlety of it.
        - > Where is that w?
        - NGKW command.
    - NG keywords selected for input
        - Example: The
                - [[midday sun]]
        - Keyword extraction is fine, but not in the direction the user wants to drill down
            - I hope you can say, "No, not that way," because this might not be something you can learn about in advance.
            - It was realized in the form of the NGKW and UPKW commands.
    - Not a good combination of keywords and questions chosen.
        - NG feedback is used as training data
    - [[Identical symbol relationship]]
    - > If the answer is that the relationship between two symbols is identical, it's not a good idea to ask questions about the relationship between symbols.
    - Wouldn't it be nice if a button appeared that said "same" and when you pressed it, the two keywords were merged as a command?
        - I'll test it properly, because I'm afraid that the disappearance of one of the keywords might cause some bug.
- State Transition Mechanism
    - How should state transition diagrams be maintained?
    - How to soften it up.
    - Beliefs about the state
            - [[partially observed Markov decision process]]
        - [[Conversation Log: State Transitions]]
        - Isn't it bad that the score you have for each word is one-dimensional to begin with? That's what I'm talking about.
                - [[Score = development, not attention]]
        - [[Keyword and question selection is an internal volume caution.]]
    - Described by a relatively small number of parameters
        - I want to make the BETTER indicators as good as possible while adhering to the MUST constraints.
        - parameter search
        - The large number of variations in the choice of questions (all of which must appear at least once) is also a constraint.
    - [[Order of appearance of the five basic questions]]
- Include attenuation in cumulative score calculation?
    - Wouldn't it be better to add attenuation? I've wondered about that.
    - On the other hand, I'm also inclined to think that if you're responding well to the first "what do you hope will happen in this dialogue", you might want to remind yourself of the key words there from time to time.
        - Often we observe cases where the first answer on this is messy.
        - It's quite common for people to get more organized as they talk and it becomes clearer what they were looking for, so don't put too much emphasis on the first statement...
- [[write_learning_pair]]
    - Hypothesis that questions that provoke long user input are good questions
    - [[Questions that do not take keywords should take features from env.]]
    - [[No means of recovery if keywords are split]]
    - [[Judgment of Awareness]]
    - [[Early design]]
    - Someone is making utterances that do not contain keywords on the first move. Now I'm asking questions without keywords anyway to avoid errors, but I might as well direct them to help since they don't seem to understand how to use it in the first place.
        - There are cases where people don't understand "digging for keywords," and there are cases where people want to bully the program.
            - [[Conversation termination from the program's side]] Maybe we could.
    - If you cut too much with NGKW before the keywords are developed, the "fountain has dried up".
        - Maybe we are in a vicious cycle of using NGKW so much that the keywords are depleted, the program jumps to a keyword from the most recent statement and asks a question, which is off the main topic, so it is NGKWed again.
        - How can we successfully lead them to the state of being crowded with lots of keywords?
        - Show the percentage of the value to be achieved in each phase?
        - Point out that there are too few keywords and the pace of NGKW is too fast?
            - We could make it so that when there are few keywords, you have to wait a bit before you can press the button.
                - [[lull (e.g. in the rain)]]
- It would be nice if questions could specify some of the answers.
    - Is it the same? No?" displays the "Same" button
        - When selected, it functions as a merge command for keywords.
    - Is this a good place to end?" should be "yes" or "no".
        - That selection can be used directly for training data.
- [[ppoi]]
    - Read back and update
- Add a RAKE-like element to keyword extraction
    - Extract long sequences that appear in your own past statements/past logs/Scrapbox



- [[pKeicho-done-2021-02-05]]


---
[[Keichobot History]]

> This is software that helps you verbalize and retrieve "what is already in you but not yet verbalized" and is not intended to give you answers to your questions.


Keywords:.[[chatbot]]  <img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>

- [[key use case]]

- [[pKeicho word frequency]]  /  [[Word frequency in source code]]

-----
- [[Calling from the export tool?]]
- [[Move to local environment?]]
-----

- [[pKeicho-Mattermost-done]]


- [[Keicho-Mattermost State Transitions]]
[[Keicho-CUI: kw type]]
- [[(6/2019)Keicho Study]]
- The number of keywords taken is indefinite (0 or 1) only with respect to the phase.
    - Maybe we should split it into two questions.

[[pKeicho-done]]
Don't we need pairs of input rows and keyword extraction results? →done



---
This page is auto-translated from [/nishio/pKeichobot](https://scrapbox.io/nishio/pKeichobot) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.