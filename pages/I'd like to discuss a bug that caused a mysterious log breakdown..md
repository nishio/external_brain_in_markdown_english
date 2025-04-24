---
title: "I'd like to discuss a bug that caused a mysterious log breakdown."
---

summary
- I had a bug that I didn't understand, so I asked for help with a problem.
- The initially perceived "log breakdown" turned out to be an incorrect perception of the phenomenon.
    - Correct: "The log splits into two conversations."
- It's a relief to know that the logs haven't been lost.

<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>What would you like to see happen in this conversation?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I'd like to discuss a bug that caused a mysterious log breakdown.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>What kind of "bug" is this "bug"?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>The first few lines of the log were lost. Even the data stored on the server lost the beginning of the log.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>What kind of "log" is that "log"?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Conversation Log. A list of what the user typed into the chat and what the bot responded to.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>Is there anything else about that "log"?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>In the first place, the server is supposed to send a single line of statements to the server, and the server side is supposed to do the postscript, so it's puzzling why it breaks off in the middle of the statement.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>
- >  Conversation logs. A list of what the user typed into the chat and what the bot responded to.
- Where is this "log" located?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>on the server.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>What kind of "server" is this "server"?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Receive a string on Heroku and return a reply response. The status is stored in Firestore.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>What kind of "save" is that "save"?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>The KVS is keyed to the talk ID, and the internal state necessary to continue the conversation is converted to JSON and stored there. JSON is the historical background, and when actually used, it is necessary to convert it into a form that can be entered into the Firestore before saving it.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>What is it that you value?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I would like to see the bugs worked out. Losing logs is a loss, and I can't use it safely if I think it might be lost. I've tried a few quick and suspicious operations, but I can't reproduce them and I'm having a hard time keeping my head above water.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>Where is that "log" located?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Firestore.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>
- >  I would like to see the bug resolved. Losing logs is a loss, and I can't use it with confidence if I think it might be lost. I've tried a few quick and suspicious operations, but I can't reproduce them, and I'm having a hard time keeping my head above water.
- What does this "log" look like?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Files to be appended. If the log disappears, you'd think it was overwritten, but it's inexplicable that it disappears because it should have been loaded, added, and written back in the first place.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>Where do these "logs" come from?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Let's see, the feature that I think is suspicious this time is the "open and continue past conversations" feature that I recently added, and I was using it all the time when the logs actually disappeared. When I used this feature, I first accessed Firestore with the conversation ID in the browser's IndexedDB to retrieve the past logs and display them.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>How do you know its "log"?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I'll send the conversation ID to Firestore and say, "Give me the log of this conversation."
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>What would you like to see happen with respect to that "log"?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I wish it would not disappear, or at least know how to reproduce the disappearing phenomenon. If you can't reproduce it, you can't debug it.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>What needs to happen to the "log" for that to happen?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I don't know!
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>
- >  I'll send the conversation ID to Firestore and say, "Give me the log of this conversation."
- What kind of "Firestore" is this "Firestore"?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Just a KVS on a server
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>Is there anything else you can tell us about that "server"?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I have a script that downloads the values on the server locally to make it easier to investigate, and I did see that the beginning of the log in question was broken using that, but then a few other things were downloaded. I should also see what kind of data those are.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>How do you know its "server"?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>That's the best way to know what the servers are up to.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>Where is this "server" located?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I'm going to go observe a local copy.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>
- >  That's the best way to know what's going on with the servers.
- What do you hope will happen regarding this "server"?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Okay, the log isn't missing, it's split into two conversations.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>What kind of "conversation" is that "conversation"?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>In other words, I thought I was having one conversation, but some kind of malfunction or something caused me to start another new conversation in the middle of the first one.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>Is there anything else about that "conversation"?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I just looked at the list of past conversations saved in my browser, and sure enough, there were two conversations. I didn't notice that, and I displayed the log at the time the second conversation ended, so only the log of the second half of the conversation was displayed, and I thought, "The first half is lost? I guess I misunderstood. I could see the log of the first half without any problem.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>How do you know its a "conversation"?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Good thing I added the past conversation list feature. You can see it there.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>What does that "conversation" sound like?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Unlike verbal conversations, which can be erased, I think it's important to keep a log and be able to read it back later. So it's a written image. That's why I was so worried when I heard, "The log is gone? but I am relieved to know that it has not disappeared for the time being.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>Where does this "conversation" come from?
---
This page is auto-translated from [/nishio/謎のログが途切れるバグが起きたので相談したい](https://scrapbox.io/nishio/謎のログが途切れるバグが起きたので相談したい) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.