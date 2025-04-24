---
title: "Proactive Slack bot"
---

- [[proactive]] [[Slack bot]].

<img src='https://scrapbox.io/api/pages/nishio-en/o3-mini-high/icon' alt='o3-mini-high.icon' height="19.5"/>
- Consider designing the implementation of Slack bot to be a mechanism where events are stored in a queue and processed sequentially by AI agents when there is enough time, instead of the conventional "react to mentions" reactive method.
- This mechanism is designed to achieve [[cooperative multitasking]] and proactive behavior ([[autonomous action]] with periodic execution tasks).
- Presented sample code using Python asyncio and explained how to receive and process events using [[Slack RTM API]].

[https://chatgpt.com/c/67aa052b-7964-8011-8fa7-c761602ef157](https://chatgpt.com/c/67aa052b-7964-8011-8fa7-c761602ef157)

---
This page is auto-translated from [/nishio/プロアクティブなSlack bot](https://scrapbox.io/nishio/プロアクティブなSlack bot) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.