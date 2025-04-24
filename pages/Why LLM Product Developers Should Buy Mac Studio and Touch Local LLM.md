---
title: "Why LLM Product Developers Should Buy Mac Studio and Touch Local LLM"
---

[Why LLM product developers should buy Mac Studio and touch local LLM｜erukiti](https://note.com/erukiti/n/n58a8180ea9fb)
Why [[LLM product developers]] should buy [[Mac Studio]] and touch [[local LLM]].
<img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/>
In LLM product development, local LLMs cannot be ignored. For fast verification of LLMs on a local machine, [[Mac Studio]] with its large amount of memory is a good choice.

The main reasons are as follows
1. state-of-the-art LLM is no longer GPT-4, but Claude3 Opus, Haiku, etc. are superior.
2. Apple Silicon's [[UMA]] allows most of the memory to be allocated to GPU memory to run large LLMs.
3. this year, local LLMs of a practical level have appeared, such as [[Command-R+]] and [[Llama3:70b]].
4. the API cost of LLM is high, but the cost can be ignored for local execution.
5. 64GB or more GPU memory is desirable for large scale LLM verification, but NVIDIA is difficult to set up. On the other hand, Mac Studio is easy to use.
6. LLM product development requires a huge amount of experimentation and it is preferable that the company provide the machine.

NVIDIA machines are good choices, but Mac Studio excels in ease and affordability. To keep up with the race to develop the most advanced LLM products, it is recommended to use Mac Studio to work with local LLMs.

> [mutaguchi](https://twitter.com/mutaguchi/status/1783271081681580482)
>  I was looking at the hatchet comments on the "Why LLM Product Developers Should Buy Mac Studio and Touch Local LLM" article, and it's interesting how little they understood....
<img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/>
It can be summarized as follows
1. the background of the growing practicality of local LLM is the running cost of proprietary LLM, the problem of leakage of sensitive information, and the BAN problem.
- Inference performance is important for local LLM product development, which requires fast memory at the VRAM level. Currently, Mac Studio is the best choice.
3. the day is near when local LLMs will work on household level devices, but developers should proceed with validation and development using Mac Studio now. Cost is lower than cloud computing.
4. local LLM products are less likely to be for sale and will often be developed for in-house use.
- The design of commercial LLM and local LLM are very different. Local LLM can be used like an API that can be called easily.

So, you are saying that developers should quickly move forward with verification and development using Mac Studio in response to the increased utility of local LLM, but that it is expected that this will be primarily for in-house use.
---
This page is auto-translated from [/nishio/LLMプロダクト開発者がMac Studioを買ってローカルLLMを触るべき理由](https://scrapbox.io/nishio/LLMプロダクト開発者がMac Studioを買ってローカルLLMを触るべき理由) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.