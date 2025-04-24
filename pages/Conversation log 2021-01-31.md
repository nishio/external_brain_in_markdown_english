---
title: "Conversation log 2021-01-31"
---

When I asked for advice on how to write a test, I was asked where the test was located, and when I tried to answer that it was the same as an existing test, I realized that it didn't have to be the same.
[https://keicho.netlify.app/#talk=hWLZQImnEQxmsWK4WDC8](https://keicho.netlify.app/#talk=hWLZQImnEQxmsWK4WDC8)

<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>What would you like to see happen in this conversation?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I'm thinking of making a slightly large-impact modification to this chat system, and I think it will probably work, but I'm wondering how to write a test, and I'd like to discuss it with you.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>What type of chat system is that?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Repeat questions for keywords and dig deeper.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>What type of keywords are those?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>It's tied to an important concept in the user's mind.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>What type of user is this user?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>NGKW Users
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>What type of concept is that concept?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Still ambiguous
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>
- >  I'm thinking of making a modification to this chat system that will have a slightly larger impact, and I think it will probably work, but I'm wondering how to write a test for it, so I'd like to discuss it.
- Is there anything else you would like to share about this chat system?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I would like to figure out how to test this. Questions about the relationship between keywords should be asked after each keyword has been drilled down, but currently, when a keyword with a very high attention score appears, the relationship between it and a word that has not been drilled down is asked.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>Is there anything else you can tell us about those keywords?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Newly appearing words have a low attention score. Repeated occurrences will be higher. Should be developed by digging deeper before asking relationship questions.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>What type of word is the word?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Same as keyword
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>Where are those keywords?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>It is in the user's text.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>
- >  Same as keyword
- How do you know these keywords?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I'm more interested in discussing testing methods.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>What type of test is that?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I want a test that can confirm what kind of bad situation we're in, and that the fixes have improved it, and automatically confirm that this case hasn't gotten worse when we tweak things in the future.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>Is there anything else you can tell us about that test?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>It is difficult to write a test because it is not the kind of test that says, "When there is an input like this, react like this," and I don't know how to write it.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>Where is that test located?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I was going to put it with the other obvious tests... but maybe that's a mistake? Maybe I should stop making implicit assumptions about the test runner I'm using now?
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>Where is that test located?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>You can either cut another folder and put the non-question-by-question test in there.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>How do you know that test?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>What I wanted to test was "no questions asking about relationships before digging questions" or "no bias towards one question type or one keyword", so I wonder if I could pour user input from the logs to test the former kind of back-and-forth conditions, or get statistics for the latter?
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>What is it that you value?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Testing increases the speed of product growth by providing peace of mind when making modifications that have a large scope of impact.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>What does that test look like?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Like a helmet or knee pads to wear when practicing roller skating. Reduces the risk of injury.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>
- >  Testing increases the speed of product growth by providing peace of mind when making modifications that have a large impact scope.
- What should happen with this test?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>It is good to be able to describe in the above way what is difficult to describe in each question.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>What needs to happen for that to test?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>If the final test returns a true/false value, it can be integrated with conventional tests, but there are still some that do not, so it is necessary to separate them from the current tests once they are in place
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>Can that test do it?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Then we'll do it tomorrow.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>
- >  If it eventually returns a true/false value, it can be integrated with conventional tests, but some still do not, so it is necessary to separate it from current tests for once
- Where does this test come from?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>(typo for "can be done")
---
This page is auto-translated from [/nishio/会話ログ2021-01-31](https://scrapbox.io/nishio/会話ログ2021-01-31) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.