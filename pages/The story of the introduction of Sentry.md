---
title: "The story of the introduction of Sentry"
---

The story of the introduction of [Sentry
- I put it on the client side this time, but I thought it would be better to put it on the server side as well.
- I realized I should send an additional dialogue ID, both server-side and client-side.

[https://keicho.netlify.app/#talk=liJIAQmmJQIuUkKijd6d](https://keicho.netlify.app/#talk=liJIAQmmJQIuUkKijd6d)

<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>What would you like to see happen in this conversation?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I want to talk about the introduction of Sentry.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>What kind of "Sentry" is this "Sentry"?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>It is a function that tells the developer when an error occurs in the user's browser.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>What kind of "user" is this "user"?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>When the user is me and I am operating on a PC, I can see the error log without doing anything, but not at other times, so I needed a system like this.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>Is there anything else you can tell us about that "user"?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>The system does not transmit the contents of errors when they occur, so the system itself has to have a function to tell the user.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>What kind of "error" is this "error"?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>For example, I recently added a function to resume the previous conversation, and I'm having a problem where the error does not occur on my development machine, but only on the user's machine where the "previous conversation" does not exist.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>Is there anything else you can tell us about that "error"?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>It also records what kind of operation caused the error, so debugging progress can be made.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>Where is the "error"?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>In the hands of the user
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>How do you know its "users"?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I don't know who exactly the user is, but I do know the browser, OS, etc.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>Where is this "user" located?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>So you're so far away from me that I can't observe you directly.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>What is it that you value?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>The idea is that detailed and prompt notification of errors that occur at a user's fingertips at a distance will make it easier to find and solve problems.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>How do you know its an "error"?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>You will be notified by e-mail.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>
- >  I'm just saying that detailed and prompt notification of errors that occur at a user's fingertips at a distance will make it easier to find and solve problems.
- Where is this "error"?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>On the user's hand browser, oh, yes, we can have the same notification of errors on the server, so we should do that too. For the value of noticing quickly.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>What would you like to see happen with respect to that "error"?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Hopefully this will be resolved quickly.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>What needs to happen to the "error" for that to happen?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>It would be nice to be notified with a set of information needed to resolve the issue.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>As for "errors," can you do that?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>It's unknown what would suffice as the required information. Those on the server would be better off sending the dialogue ID.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>
- >  On the user's hand browser, oh, yes, we can have the same notification of errors on the server, so we should do that too. For the value of noticing quickly.
- Where do these "users" come from?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I'm not getting a specific user, so I guess I'd better send the dialogue ID in the client version.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>Where is this "user" located?

---
This page is auto-translated from [/nishio/Sentryを導入した話](https://scrapbox.io/nishio/Sentryを導入した話) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.