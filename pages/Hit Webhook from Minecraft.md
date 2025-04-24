---
title: "Hit Webhook from Minecraft"
---

[https://github.com/Akenland/SimpleWebhooks](https://github.com/Akenland/SimpleWebhooks)
config.yaml

```yaml
webhooks:
  other:
    test:
      url: https://mattermost.example.org/hooks/XXXXXXXX
      json:
        text: "hello!"
```

(computer) command
- `webhooks execute test`
result
- I received it in Mattermost, a Slack clone, and it will work in Slack too.
- ![image](https://gyazo.com/cd5205e3479adb70b38b7db760ff9917/thumb/1000)


Almost all services that have Incoming Webhooks can be triggered from the microphone.

---
This page is auto-translated from [/nishio/MinecraftからWebhookを叩く](https://scrapbox.io/nishio/MinecraftからWebhookを叩く) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.