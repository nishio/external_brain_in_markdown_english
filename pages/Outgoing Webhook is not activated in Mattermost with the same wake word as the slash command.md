---
title: "Outgoing Webhook is not activated in Mattermost with the same wake word as the slash command"
---

from  [[Chatbots in Mattermost]]
Outgoing Webhook is not invoked with the same wakeword as the slash command in [[Mattermost]].
    - Even if the POST fails, there should be a record in the http.server log, but there isn't.
    - It doesn't even show up on the ngrok display.
    - Suspicion that the request is not flying.
- [https://docs.mattermost.com/developer/webhooks-outgoing.html#troubleshooting](https://docs.mattermost.com/developer/webhooks-outgoing.html#troubleshooting)
    - > To debug outgoing webhooks in System Console > Logs, set System Console > Logging > Enable Webhook Debugging to true and set System Console > Logging > Console Log Level to DEBUG.
    - But it doesn't show up in this log either.
- It doesn't appear to be activated by the same wake word as the slash command.
    - Cannot use both `/nisbot` and `nisbot foo` at the same time

---
This page is auto-translated from [/nishio/Mattermostでスラッシュコマンドと同一のウェイクワードではOutgoing Webhookが起動されない](https://scrapbox.io/nishio/Mattermostでスラッシュコマンドと同一のウェイクワードではOutgoing Webhookが起動されない) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.