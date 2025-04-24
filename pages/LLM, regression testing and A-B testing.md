---
title: "LLM, regression testing and A/B testing"
---

2023-03-06
    - Conversation log with a version of [[Keichobot, a chatbot that brings out your ideas]] that uses the ChatGPT API

## one-line summary
.
- Systems written in natural language prompts can be easily improved by non-engineers at first glance, but a [[regression test]] mechanism is necessary because an unmaintainable hell awaits them. LLM] is also necessary for the regression test. On the other hand, combining with [[A/B Test]] also expands the possibilities.


## summary ver.1 (human modified)
.
- Prompts written in natural language need to be improved.
    - Easy to implement ad hoc addition of rules
    - But there are software engineering problems with that.
    - After fixing the prompt, we need to verify that the problem has been resolved and that other problems have not recurred.
- In other words, a regression test is needed.
    - Regression testing on natural language output requires the use of LLM
- Combination with A/B testing is also effective
    - No need to define good behavior for natural language prompts using LLMs
    - But on the other hand, the use of LLM expands the scope of what A/B testing can cover.


## Summary ver.1 by ChatGPT
.
- Need to improve natural language prompts
- Implementation of ad hoc addition of rules is problematic from a software engineering perspective
- Need to verify that it will not recur after correction.
- A/B testing is useful to define good behavior for natural language prompts and does not need to be defined using LLM
- No new approach is proposed.

## Summary ver.2 by ChatGPT
.
- I was consulted about a system modification.
- The implementation method of adding a modification rule is subtle.
- Step 1: Verify that the correction no longer causes undesirable behavior
- Step 2: Confirm recurrence with regression testing
- Step 3: Perform a mechanical decision test using LLM
- A/B testing approach is also effective in determining whether modifications are necessary.
- Enables quantification via LLM for natural language that has been difficult to quantify

## log
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>What would you like to see happen in this conversation? (GPT)
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>I want to organize my thoughts by talking.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>To achieve your goal of organizing, ask questions to dig into the user's inner issues to form specific ideas.
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>🙁
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>You want to organize your thoughts, you can ask questions to clarify what is confusing and what you need to think about.
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>Fixing undesirable behavior of systems implemented with natural language prompts
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>Can you tell us specifically what behavior occurred?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>The system for listening to the user was all over the place denying what the user said.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>That can feel like an unpleasant experience. What modifications do you expect to make from that experience in the future?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>At any rate, I added "Don't deny the user" to the natural language prompt, but I thought this was subtle from a software engineering perspective.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>Indeed, the expression "don't deny the user" is very subtle. Can we look for ways to improve the system by modifying its algorithms so that it doesn't happen?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>No, not that the expression is subtle, but that the implementation style of adding rules ad hoc is not good. The source code becomes bloated and no one knows which code is useful and which is useless.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>Understood. Regarding the modification, is it possible to check for the presence of negative words in the user's statement to the algorithm and improve the algorithm to avoid them?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>You spoke two steps ahead of what I was trying to explain, W. Yes, but the reader can't keep up, so let's go step by step. The current "simply add a rule" is not verified to see if it made it better. First of all, it is necessary to verify whether the "undesirable behavior" has been prevented by the modification by including the data of when it occurred. This is Step 1
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>Understood. So step 1 is to verify that the "undesirable behavior" no longer occurs after the correction is made. What data should be collected for this purpose?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>User input and system output in response. And step 2 is that regression testing is necessary to know that the "undesirable behavior" has not recurred after it has stopped occurring, and it is not enough for a human to visually determine whether it has or has not occurred.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>Understood. So step 2 is to perform regression testing to confirm recurrence. What specific tests should be performed?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>A test is needed in which a machine, not a human, determines whether it is OK or NG. However, in this case, since the output is a natural language sentence, it is difficult for a human to write the conditional expression in code. I think we have no choice but to use LLM here as well. This is Step 3
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>Going back to what you said earlier, what specific tests should be performed in relation to modifying the natural language prompts?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>Specifically, it generates an answer to a given input with the current parameters, gives that answer to a given LLM with the prompt "Does this answer negate the user's statement?
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>The test you mentioned seems to determine the negation of the answers given by the system, but what are some other points to keep in mind when the system answers besides such a test?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>That aside, let's wrap up the story so far.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>I think the summary of our discussion is that natural language prompts need to be modified, that ad hoc addition of rules is subtle from a software engineering perspective, that modification requires recurrence testing, and that the use of LLM is necessary.
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>Yes, it is. And if we can get to that point, improving natural language prompts to avoid "bad behavior" can be done with proper verification.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>Thank you for your attention. What would you like to talk about?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>I'm going to go further here 🙁 I want to sort this out so listen first.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>Yes, sir, we have heard you. We will ask questions from here about steps the client can take to become more specific.
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>I think it could be connected to the A/B testing approach.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>I think it is more necessary first to have concrete outputs about improving natural language prompts before we can think about connecting with A/B testing approach. What approach do you need to take to be able to concretize what you want to communicate?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>Do not deny the user's statement!
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>Sorry, my previous response was incorrect. So, I would like to ask again, regarding the improvement of natural language prompts, I think it is more necessary to have a concrete output first. What approach do you need to take to be able to concretize what you want to communicate?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>I'm not sure if we should include a fix for a certain prompt 🙁 We could try to include it for some users and see if it reduces undesirable behavior.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>Okay, that is a well thought out approach. It would seem that a good approach would be to modify the natural language prompts for a small number of users and then verify whether the undesirable behavior has been reduced. So what steps would be needed to do this?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>After writing this, I think you're making a bit of a leap. The definition of "desirable" does not have to be based on LLMs; a system using LLMs can also use withdrawal rates, click-through rates, and even have an explicit good/bad feedback button by the user. There is just a new means of defining "LLM sees and judges" added to the mix.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>Understood. There is an approach of doing A/B testing to have concrete outputs, but you don't have to use LLM to define the preferred behavior, you can use withdrawal rates, click rates, explicit feedback buttons, etc.
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>Is it appropriate to say "LLM is effective in increasing the scope of A/B testing" rather than "A/B testing is effective in improving systems that use LLM?"
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>Thank you. I would like to ask again, would you say that "LLM is effective in increasing the scope of A/B testing"?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>That is true. Because natural language, which has been difficult to quantify, can now be quantified via LLM.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>You have successfully presented various approaches. So, are there any better directions or new approaches that could be organized so far?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>We'll get to that another time. Bullet point summary of the conversation so far.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>To summarize what you said, the modification of natural language prompts requires specific outputs such as defining preferred behavior and identifying target users, and there were suggestions for an A/B testing approach and the use of LLM. In addition, when asking questions, it is important to look for key concepts and ask questions related to them.
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>(You didn't make it.
- <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Let's add a separate function to generate a summary.

[https://keicho.netlify.app/#talk=8pZW2kyh27C7lgy9VH4v](https://keicho.netlify.app/#talk=8pZW2kyh27C7lgy9VH4v)
#KeichobotLog

---
This page is auto-translated from [/nishio/LLMと回帰テストとA/Bテスト](https://scrapbox.io/nishio/LLMと回帰テストとA/Bテスト) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.