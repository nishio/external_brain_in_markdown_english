---
title: "The scale of demand makes a difference in the efficiency of GPU use."
---

> [nishio](https://twitter.com/nishio/status/1712115074712952953/quick_promote_web/intro) GPUs are an expensive resource, and there is a limit to the throughput that a single GPU can deliver, so the world as a whole has a Service providers with sufficient demand can use GPUs efficiently by leveling the load, and service providers without sufficient demand can use GPUs inefficiently by many times because they let GPUs idle during low load times.

[[load leveling]].

<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>This text points out issues related to the efficiency of GPU (graphics processing unit) usage.
- GPUs are expensive resources: GPUs are high-performance computing resources that are expensive to purchase and maintain.
- There is a limit to the throughput that a single GPU can provide: Even the most powerful GPU has an upper limit to the amount of data and the number of tasks it can process at once.
- Service providers with sufficient demand from the entire world: Service providers with large global demand can distribute requests from a large number of users to the GPUs on average, resulting in more efficient use of the GPUs.
- Service providers that let their GPUs idle during low loads: On the other hand, service providers that do not receive so many user requests will see their GPUs underutilized, wasting more time and decreasing usage efficiency.

In essence, it points out that large service providers can use GPUs efficiently, while smaller service providers often do not fully utilize their GPU capacity. This is seen as a challenge to maximize the cost-effectiveness of the resource.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>That's about right.
- For a service with fewer users than ChatGPT to respond at the same response rate as ChatGPT, it would have to pay a lot more "GPU investment per user" than OpenAI
- [[economies of scale]]."

---
This page is auto-translated from [/nishio/需要の規模によってGPUの使用効率に差が生じる](https://scrapbox.io/nishio/需要の規模によってGPUの使用効率に差が生じる) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.