---
title: "Conversation Log: Design Changes"
---

[https://keicho.netlify.app/#talk=D4CWmonr9MgIabczTGNx](https://keicho.netlify.app/#talk=D4CWmonr9MgIabczTGNx)

<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>What would you like to see happen in this conversation?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Listen first.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>Yes, sir.
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>It's not that I'm worried about this, it's more like a design change that I'll have to do with this kind of policy, and I'll write it down so that my future self can easily understand it.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>Policy."
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Now, for each question/keyword pair, the system calculates the score that should be used and produces the one with the largest score.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>Score."
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>In that case, however, questions that do not take keywords would have a constant score
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>Score."
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Therefore, we are considering redesigning the system to calculate the score using the environment as an argument. I will delegate the specific calculation to the question.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>Score."
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>the end
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>What would you like to see happen in this conversation?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I thought it would be easier to understand when I look back in the future if we continue to verbalize the information.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>What kind of "future" is that "future"?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>You know how sometimes after a year or so you don't know why you designed the way you did? This change is a bit non-intuitive, so I thought I'd better leave it written down.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>
- >  So, I am thinking of redesigning it so that it calculates the score using the environment as an > argument. I will delegate the specific calculation to the question.
- What "score" is this "score"?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Scores higher when you decide it's a good idea to ask that question.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>What is it that you value?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Questions that do not take keywords should be able to have a higher score depending on the situation. With the current constant score, if you have a high score, you have to make it low because it will keep coming up. If it becomes a function that takes environment as an argument, it can be improved.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>What kind of "question" is that "question"?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>This time I am particularly thinking about the feedback "You have few keywords". This is something that should be sent out or not based on how few keywords are extracted
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>What kind of "keywords" are those "keywords"?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>This system extracts keywords from the user's input and asks questions in response to them, but if the amount of those keywords is low, the conversation will not be very lively. Often users fall into such a pattern, so I think it would be good to give them feedback that they should speak up to increase the number of keywords.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>Is there anything else you can tell us about that "keyword"?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Today, I have tried to extract those that include verbs, but that still does not take care of users who make short, low-content statements. I am thinking that it would be better if we gave direct feedback that more words is a good thing.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>
- >  Score higher when you decide it is a good idea to ask that question.
- Is there anything else you can tell us about this "score"?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>As for that specific feedback, I am thinking that while the keywords extracted are less than 30, the score should be higher as the number of turns progresses. And once they appear, they are consumed.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>Where is the "score"?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>The algorithm for score calculation varies from question to question, so we are thinking of delegating to an object for each question
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>Is there anything else about that "question"?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Questions are now object-oriented and made of objects, but reuse using inheritance is not easy to read, and the results do not change from instance to instance, so dictionary lookup by question ID may be a better option.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>How do you know what the "question" is?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Questions are differentiated by question ID.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>What should happen to that "question"?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Especially if questions that don't take keywords, which are currently underutilized, could be more easily utilized.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>What needs to happen to that "question" for that to happen?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I'd like to see the score fluctuate based on the situation.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>Can that "score" do it?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>This new score calculation mechanism can do that.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>
- >  I'd like to see the score fluctuate based on the situation.
- Where does this "score" come from?

---
This page is auto-translated from [/nishio/会話ログ:設計の変更](https://scrapbox.io/nishio/会話ログ:設計の変更) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.