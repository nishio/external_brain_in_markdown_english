---
title: "Toolformer/Visual ChatGPT/HuggingGPT/TaskMatrix.AI"
---

> [mi141](https://twitter.com/mi141/status/1643909035664773120/photo/1) I'm interested in a method based on GPT/ChatGPT that makes good use of multiple external APIs (and other underlying models) to solve various tasks. I was interested in a method to solve various tasks based on GPT/ChatGPT
>  ・ [[Toolformer]].
>  ・ [[Visual ChatGPT]].
>  ・ [[HuggingGPT]].
>  - [[TaskMatrix.AI]] (This is shown in the figure below)
>  I read around. Mainly I wanted to know how to learn how to use the API!
>  ![image](https://pbs.twimg.com/media/FtBUryWakAM3txd?format=jpg&name=medium#.png)

> [mi141](https://twitter.com/mi141/status/1643909038042906624) Toolformer learns how to use APIs by fine-tuning, preparing special tokens for APIs and creating datasets containing them successfully and automatically. The API can be used to solve tasks that require numerical computation and knowledge.
>  However, the cost of adding or removing new APIs is high because fine-tune is required.
>  ![image](https://pbs.twimg.com/media/FtBOwuKaMAAzX_d?format=png&name=900x900#.png)

> [mi141](https://twitter.com/mi141/status/1643909040379162625) [[Visual ChatGPT]] is a truly prompt engineering approach, where the type of API and its usage is written in the prompt. Naturally, additions and deletions are easy, and the various APIs, including image generation and editing, can be successfully used to follow the user's instructions.
>  However, this time the number of usable APIs is limited by the length of the prompt.
>  ![image](https://pbs.twimg.com/media/FtBP85ZaYAADHku?format=png&name=small#.png) ![image](https://pbs.twimg.com/media/FtBR-eEakAAvKm_?format=jpg&name=small#.png)
- I wonder if [[ChatGPT Plugins]] works the same way.
- I guess I'll just have to pile on the prompt since the plugin I just created will be used as soon as possible.


> [mi141](https://twitter.com/mi141/status/1643909043449384962) [[HuggingGPT]] is a similar approach. However, this one needs to be able to handle a very large number of APIs due to the concept of mastering the models in [[HuggingFace]]. Therefore, it seems that the API candidates are filtered in advance (in the Model Selection section of the figure), and only the results are included in the prompts.
>  ![image](https://pbs.twimg.com/media/FtBSOGuaIAAzaRJ?format=jpg&name=large#.png) ![image](https://pbs.twimg.com/media/FtBSZRGaAAEiM8c?format=jpg&name=small#.png)

> [mi141](https://twitter.com/mi141/status/1643909046506864640) The last is TaskMatrix.AI, which seems to use the appropriate API by searching as needed from a database with registered APIs! (No detailed description...)
>  It is possible to handle so many APIs (the title says Millions of APIs) because it is not a way to write to a prompt.
>  ![image](https://pbs.twimg.com/media/FtBTKpiaMAAWGvP?format=jpg&name=medium#.png)

> [mi141](https://twitter.com/mi141/status/1643909049447247872) Well, as it turns out, 3/4 were Microsoft studies (and all published 2023/03), but it was interesting to trace the transition along with the motivation. ChatGPT as a hub for multiple infrastructure models is fascinating.
>  [https://arxiv.org/abs/2302.04761](https://arxiv.org/abs/2302.04761)
>  [https://arxiv.org/abs/2303.04671](https://arxiv.org/abs/2303.04671)
>  [https://arxiv.org/abs/2303.17580](https://arxiv.org/abs/2303.17580)
>  [https://arxiv.org/abs/2303.16434](https://arxiv.org/abs/2303.16434)

---
This page is auto-translated from [/nishio/Toolformer/Visual ChatGPT/HuggingGPT/TaskMatrix.AI](https://scrapbox.io/nishio/Toolformer/Visual ChatGPT/HuggingGPT/TaskMatrix.AI) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.