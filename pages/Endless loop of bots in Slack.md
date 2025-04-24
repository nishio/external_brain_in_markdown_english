---
title: "Endless loop of bots in Slack"
---

- Messages displayed in replies to Outgoing Webhooks in [[Slack]] also generate Outgoing Webhooks
    - That's not the case at Mattermost.
- So a [[bot (autonomous computer program, esp. on a network)]] that speaks without a trigger word will be triggered by its own statement and speak again
- It appears to be limited to once per second, but that's not an essential solution.
- Outgoing Webhook statements will be usename to the slackbot, so just ignore them in that case.

---
This page is auto-translated from [/nishio/Slackでのボットの無限ループ](https://scrapbox.io/nishio/Slackでのボットの無限ループ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.