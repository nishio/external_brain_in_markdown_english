---
title: "shoya140/chatgpt-slack-bot"
---

[/villagepump/2023/03/29#64241b37e1daa500001c217b](https://scrapbox.io/villagepump/2023/03/29#64241b37e1daa500001c217b)
from [/villagepump/2023/03/29](https://scrapbox.io/villagepump/2023/03/29)
- The deploy destination is[[Heroku]]かな<img src='https://scrapbox.io/api/pages/villagepump/takker/icon' alt='/villagepump/takker.icon' height="19.5"/>
    - I've included a configuration file that assumes Heroku!<img src='https://scrapbox.io/api/pages/villagepump/shoya140/icon' alt='/villagepump/shoya140.icon' height="19.5"/>
        - [Socket Mode](https://api.slack.com/apis/connections/socket) so you can try it on a local PC, etc. without having to change Slack settings.
        - I'm running it on Heroku's [[Eco dyno]] for now.
            - [[Heroku's 30-second timeout]] で死んでしまうことが…<img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>
        - If it takes more than 30 seconds, don't worry about it.[[Worker dyno]]を使っています<img src='https://scrapbox.io/api/pages/villagepump/shoya140/icon' alt='/villagepump/shoya140.icon' height="19.5"/>
        - I see!<img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>

---
This page is auto-translated from [/nishio/shoya140/chatgpt-slack-bot](https://scrapbox.io/nishio/shoya140/chatgpt-slack-bot) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.