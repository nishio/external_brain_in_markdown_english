---
title: "Consider explaining the new features."
---

A new command called "UPKW command" was created today, and I will consider explaining it.
- I wanted to explain a new feature, but he started talking about "how it used to be" or something like that.
    - This is an inadequate explanation of the user perspective
- After plowing through, the "what is the value?" question verbalized something close to user value.
    - I realized that the explanation to the user should bring this to the front of the line more often.

<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>What would you like to see happen in this conversation?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>A new command called "UPKW command" was created today, and I will consider explaining it.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>What type of UPKW command is that UPKW command?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Up until now, when it was running as a bot in an existing chat, such as Slack, the commands were entered by a human as a string. So they were short strings, and basically took no arguments, and were targeted to the keyword selected immediately before the command. The implementation that took arguments was implemented, but it was not used because it was too cumbersome.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>What kind of Slack is that Slack?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>A text-based user interface, also known as CUI.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>What type of user interface is it?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>In creating the Web version, we decided to create our own user interface, and the idea naturally came to us that it would be a good idea to install the commands as buttons.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>Is there anything else about its user interface?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Even commands that take arguments can be made into buttons for each argument.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>What type of command is that command?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>The first command I implemented was the NGKW command, which "removes keywords used in the previous question when they are keywords you don't want to dig into.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>Is there anything else about that command?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>This led to the idea that it would be nice to have a "command that tells the user to ask for more of a keyword that was not used in the previous question".
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>Where is that command?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>They are lined up as buttons below the input fields. So you can separately present "keywords that were not chosen" that do not appear in the chat document.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>What type of keywords are those?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Keywords extracted from user input.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>Is there anything else you can tell us about those keywords?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Users implicitly have keywords that they want you to dig into and keywords that they don't. By actually being asked a digging question, what they want you to dig into becomes an output and observable as a response of "No, don't dig into that" or "Ask me more about this".
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>What is it that you value?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Software that can do this is valuable, and the UPKW command is valuable because it contributes to this.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>Is there anything else about that UPKW command?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>If used, the target keyword is more likely to be used in the question. The information that a user pressed this button is information that the user values the keyword selected by the button more highly than the keyword selected immediately before it, so if a lot of this information is collected, it could be used to improve the keyword selection algorithm.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>Where are those keywords?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>This is a button that expresses the feeling that the chosen keyword itself is not bad but the question just before is not so good 🙁.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>What type of last minute is that last minute?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>NGKW Last minute
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>
- >  We want to encourage the output of what is not yet clearly output in humans by having software work on it, and software that can do this is valuable, and the UPKW command is valuable because it contributes to this.
- Where is this UPKW command?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Keywords are presented in a prominent position below the input field.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>
- >  We want to encourage the output of what is not yet clearly output in humans by having software work on it, and software that can do this is valuable, and the UPKW command is valuable because it contributes to this.
- Where is this UPKW command located?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>🙁
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>
- >  We want to encourage the output of what is not yet clearly output in humans by having software work on it, and software that can do this is valuable, and the UPKW command is valuable because it contributes to this.
- What does this UPKW command look like?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Mysterious communication, as if you are responding not to the words spoken by the other person, but to the words that were not spoken.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>
- >  We want to encourage the output of what is not yet clearly output in humans by having software work on it, and software that can do this is valuable, and the UPKW command is valuable because it contributes to this.
- Where does this UPKW command come from?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>When the bot selects keywords to use for a question, it internally scores them and chooses the largest one. At this time, there are keywords with high scores that were not chosen, so they are used
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>Where are those keywords located?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I'm not sure how to do this 🙁 (on second thought, I haven't implemented the server side of this command yet)
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>Where is that command located?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>UPKW Question
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>
- >  When the bot selects keywords to use for a question, it internally scores them and chooses the largest one. At this time, there are keywords with high scores that were not chosen, so they are used
- What type of question is this?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Questions to make users verbalize what is bothering them
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>Is there anything else about that question?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I think it has the effect of forcing us to move our viewpoints. By looking at things from a different perspective, new insights can be gained.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>
- >  Questions to make users verbalize their inner blur
- Where is this question?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>🙁
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>
- >  Questions to make users verbalize their inner blur
- Where is this question?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>🙁
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>
- >  Questions to make users verbalize their inner blur
- What does this question seem to be?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I used to say like a fish hook, but based on the conversation we've had so far, it's not quite the same. It's like someone who stands up and takes someone around who is sitting and thinking.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>
- >  Questions to make users verbalize their inner blur
- Where does this question come from?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>It comes from within this chat system.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>
- >  Questions to make users verbalize their inner blur
- How do you know this question?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Displayed on the phone at hand
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>
- >  Questions to make users verbalize their inner blur
- This begs the question, what should happen?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>It is good when users get a new realization, "Oh, I see.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>To do that the question needs to be what needs to happen?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>They need to be a good balance of questions that are not obvious and easy for the user to answer, but also not misguided and far removed from the user's interests.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>The question is can it?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Not entirely impossible, but not clear how it can be achieved.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>
- >  We want to encourage the output of what is not yet clearly output in humans by having software work on it, and software that can do this is valuable, and the UPKW command is valuable because it contributes to this.
- What is the relationship between this UPKW command and the question?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>A command that pulls back "not that way, this way" when the bot starts asking misguided questions. So you get closer to a "good balance".
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>What is the relationship between that command and the question?

consideration
- If this log is chopped and rearranged in Regroup, it would be a good case study.
        - [[Organize logs of listening chats by inscribing them on sticky notes.]]
[https://keicho.netlify.app/#talk=yAJxKTwc1ryiUTUbihUA](https://keicho.netlify.app/#talk=yAJxKTwc1ryiUTUbihUA)

---
This page is auto-translated from [/nishio/新機能の解説を考える](https://scrapbox.io/nishio/新機能の解説を考える) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.