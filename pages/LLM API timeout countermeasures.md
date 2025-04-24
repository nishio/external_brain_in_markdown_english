---
title: "LLM API timeout countermeasures"
---

When I said, "Search and summarize what would be a good way to design a service that hits an LLM API that might time out," he told me something more grandiose than I'd imagined.

<img src='https://scrapbox.io/api/pages/nishio-en/o3-mini-high/icon' alt='o3-mini-high.icon' height="19.5"/>
- Asynchronous processing and use of queues.
    - Asynchronize API calls and process requests sequentially in queues such as [[RabbitMQ]] and [[Kafka]].

- Timeout and retry strategies.
    - Set an appropriate timeout value and retry using the [[exponential backoff]] method.

- Introduce [[circuit breaker pattern]]
    - The call is aborted after a certain number of failures, and a periodic check is made to determine whether the call is restored.

- cache and state management.
    - Utilize cache with [[Redis]], etc., and manage circuit state with [[DynamoDB]], etc.

- [[Orchestration and Monitoring]]
    - [[AWS Step Functions]], etc. for workflow control, detailed logging and monitoring for enhanced fault response.

[https://chatgpt.com/c/67c01f64-8c18-8011-8342-ab59b1e75354](https://chatgpt.com/c/67c01f64-8c18-8011-8342-ab59b1e75354)

How to set up a Redis server
[https://chatgpt.com/c/67c016af-17d0-8011-8dd5-f1cc245b8971](https://chatgpt.com/c/67c016af-17d0-8011-8dd5-f1cc245b8971)


---
This page is auto-translated from [/nishio/LLM APIのタイムアウト対策](https://scrapbox.io/nishio/LLM APIのタイムアウト対策) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.