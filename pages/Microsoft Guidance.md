---
title: "Microsoft Guidance"
---


[[Token Healing]]
[https://note.com/nyosubro/n/n929da0047dc9](https://note.com/nyosubro/n/n929da0047dc9)
The final token in the prompt has the effect of expressing the boundaries of the token split, introducing a bias in the distribution of the generated strings that many do not expect
So, the final token of the prompt is generated without the prompt, and the final token is used as a constraint for rejection sampling.

relevance
- [[LangChain]]

---
This page is auto-translated from [/nishio/Microsoft Guidance](https://scrapbox.io/nishio/Microsoft Guidance) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.