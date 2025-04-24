---
title: "Chatbot without trigger"
---

    - Sequel to [Chatbots in Mattermost
- I was going to do the equivalent of this.
    - [Enabling interactions with bots | Slack](https://api.slack.com/bot-users)
        - [Events API | Slack](https://api.slack.com/events-api)
- I thought I might need OAuth, but actually I didn't.
- What I wanted to do in the first place was, "I don't want to have to put a trigger word in my head every time I talk to a bot."
- I assumed that I needed a trigger word to fly outside with Outgoing Webhook.
- But I should have simply left it blank.
    - (at least in Mattermost).
    - ![image](https://gyazo.com/bfd63b257ddaba638795337ed0a5258c/thumb/1000)

- I didn't quite understand this explanation:.
    - ![image](https://gyazo.com/08f5cf0239aff8355d8548157815f448/thumb/1000)
    - Cannot leave both the channel and trigger word designation blank
    - If a trigger word is specified, the channel can be unspecified.
    - Once a channel is identified, conversations within that channel can be picked up without trigger words.

therefore
- If you simply want to talk to the bot without trigger words, identify the channel
- If you simply want to execute a command with a trigger word on multiple channels, specify the trigger word.
- If you want to collect human conversations on multiple channels without trigger words, you need to hit the API
    - OAuth or Personal Access Token
would that be the case?
---
This page is auto-translated from [/nishio/トリガーなしでのチャットボット](https://scrapbox.io/nishio/トリガーなしでのチャットボット) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.