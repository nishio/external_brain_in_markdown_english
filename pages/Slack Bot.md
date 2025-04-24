---
title: "Slack Bot"
---

2018-10-05
- I'm writing in Python using slackclient.
- Watch for notifications from Scrapbox to flow into Slack
- Common bots respond immediately to input.
    - another
    - I decided to throttle it by the hour.
        - When a human types, it replies 3 seconds later.
        - If a human starts typing again within 3 seconds, wait until he/she has finished typing and 3 seconds have passed before replying.
        - Speech triggered by it after 30 seconds for your own speech as well.
        - On the side of the book botting library, "the same utterance is never made twice while the instance is alive".
            - It was too much trouble to implement something like revival over time. Just clear the memory at the appropriate time.
            - I can't touch the memory from the outside because of the closure implementation right now.
            - I'll do it when I feel like it because it's more straightforward to change to a class implementation.
- Deploying to heroku is a hassle because of dependencies on various files, so let's add a function to spit out data files for deployment.
- [[chatbot]]   [[Books as Chatbots]]

2019-06-03
[Enabling interactions with bots | Slack](https://api.slack.com/bot-users)
[[Bot]]  [[bot (autonomous computer program, esp. on a network)]]
[[Slack]]

---
This page is auto-translated from [/nishio/Slackボット](https://scrapbox.io/nishio/Slackボット) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.