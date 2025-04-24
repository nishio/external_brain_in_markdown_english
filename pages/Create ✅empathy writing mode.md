---
title: "Create ✅empathy writing mode"
---

I thought of making a [[Tutorial for making 🤔 sentences]] as an explanation of how to use Keicho-Regroup.

Instead of using Keicho as it is now, it would be better to add a mode dedicated to [[empathic writing]].
- The degree of freedom and diversity of questions will be reduced, but it is less likely that an unfamiliar user will get lost.

The design changes to achieve this would be beneficial for experimenting with [[🤔Task Management Chatbot]], which I have been wanting to do for a while. [[Template chatbotization]] would also be easy.

What we want to do
    - [[Ten questions specific to writing]].
- It's not good to just keep putting questions out there.
    - The bot needs to respond back to the question.
    - If so, at what point do we move on to the next question?
    - You can go on automatically, but it's hard to move on once the conversation gets going.
    - User should be able to pull the trigger with "next question".
    - That is, [[Allows for additional ✅ command processing]] is required.
    - And we want to display the added commands on the buttons (because it is too much to ask an unfamiliar user to learn the commands).
            - [[Create ✅ answer choices on the server side]]
- When you're done with a set of questions, export them to Regroup and move the stickies around to organize them.

What needs to be implemented
    - [[✅Change the first question on the client side]]
- How to enter the special mode
    - Load ✅URL with mode information
        - `#mode=empathy_writing`
        - [[Put 🤔 mode changes on the menu?]]
    - [[Change of initial server-side state by ✅ mode]]
    - [[✅Implemented questions and actions for empathic writing]]
- Designing the End of Empathy Writing Mode
    - Export to Regroup or continue the conversation some more?
    - Export and continue the conversation as well?
        - Two screens are for people who are used to it, but not for beginners.
        - Export once done.
    - Include a message to proceed with the export.
        - "Now that we've dug deep enough, let's do 'Export for Regroup' from the menu."
        - Oops, this menu is not on the conversation mode on your current screen.
        - ✅ attached

- I tried.
        - [[I hope it gives readers an idea of what the empathic writing mode I created today looks like.]]
        - [[Organizing with Regroup: Empathy Writing Mode Explained]]

    - [[Can't use clipboard with 🤔http?]]
- The last message causes a server error.
    - ✅Corrected.
- The part in front of it needs to be adjusted because of the dalliance.
    - Checking the score, it's getting dodgy around the 500 mark.
    - 552 just after Q10.
    - About 200 or more keywords are good for the question.
    - Score on questions that do not take arguments defaults to 50

what to do
    - [[✅Display "Next Question" button in empathic writing mode]]
    - [[✅ Free response on/off]]
- Raise the score for questions that do not take arguments.
    - Score Observation
        - Basically, a keyword with a score of 100 for the immediately preceding statement, with a last-minute bonus of 200, a naturalness of 100, and a question preference bias of 0.4 is 400.4.
        - The score for a question that does not take arguments is base 50 + naturalness 50, which is 100.
        - [[✅Treat the "next question" command as NG.]]
        - [[Score calculation for ✅-specific mode]]
- Make a question sticky when mapping ✅Regroup
    - It would be easier to do this if there were stickies like "Positive Lines."

add (e.g. annex)
    - [[The first question should be made with the expectation that it will be in the title of the log.]]
- > This mode is to assist in writing sentences. What kind of writing are you trying to do?
    - Aligned with other modes.

- Use of sophisticated description methods when implementing KPT mode has been changed.
    - ![image](https://gyazo.com/de03afb689b1c0eb35de36f4da07c600/thumb/1000)


---
This page is auto-translated from [/nishio/✅エンパシーライティングモードを作る](https://scrapbox.io/nishio/✅エンパシーライティングモードを作る) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.