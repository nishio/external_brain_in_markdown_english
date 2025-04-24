---
title: "Redis"
---


<img src='https://scrapbox.io/api/pages/nishio-en/o3-mini-high/icon' alt='o3-mini-high.icon' height="19.5"/>
The following two simple methods are recommended.

- Use Docker:
- In the official Redis image
- docker run -d --name redis -p 6379:6379 redis
- and the Redis server will be up and running in a short time!

- Install with Homebrew (for macOS):
- brew update && brew install redis
- redis-server
- You can start it in your local environment with

In addition, managed Redis in the cloud services (e.g., Amazon ElastiCache, etc.) can significantly reduce the operational load.
---
This page is auto-translated from [/nishio/Redis](https://scrapbox.io/nishio/Redis) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.