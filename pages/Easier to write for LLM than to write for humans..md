---
title: "Easier to write for LLM than to write for humans."
---

2023-04-06
> [__gfx__](https://twitter.com/__gfx__/status/1643561940848091136) You'd be surprised how often we get extremely accurate answers when we ask GPT-4 about TypeScript. I think this is probably because there are so many good TypeScript texts in the world.

> [__gfx__](https://twitter.com/__gfx__/status/1643565160328736768) However, I have no idea about the new features recently and can't get attached to them. So no satisfies will be used in the code that GPT-4 will write.
>  This gap is not so easy... for those who know what they're doing, but it might be hard to be practical.

> [omochimetaru](https://twitter.com/omochimetaru/status/1643572683320459267) than creating a new, highly functional language,
>  It is more efficient to use old languages with AI support for development,
>  I don't like the idea that this would put a brake on the evolution of the language...

> [__gfx__](https://twitter.com/__gfx__/status/1643575579508355077) That said, I think that concern is unfounded, as we have already achieved engines like bing that learn in real time.
>  Rather, I am more concerned that even if a new language is created, the sample size will be too small for AI to write well and it will not spread....

> [omochimetaru](https://twitter.com/omochimetaru/status/1643576125011165185) I see.
>  I wonder if the AI is smart enough, even if the text is only about the official specs, if it can help us understand and use new concepts from it.


> [nishio](https://twitter.com/nishio/status/1643812867773452290) The technology is already in place and will soon come down to the average consumer "[[Ability to give LLMs a knowledge package of your area of interest]]" will come down to the general public soon. When that happens, authors of new languages will create knowledge packages for LLMs, and people who want to use the language will be able to load them into LLMs and use them.
- I wrote this and implemented it in [[ChatGPT Plugins]] on 4/7, and it was provided under the name [[Assistants API]] at [[OpenAI DevDay]] on 11/7 (related: [[Retrieval-augmented Language Model]]).

> [nishio](https://twitter.com/nishio/status/1643813597792071680) Creating knowledge packages is actually easier than creating documents for human readers. Because humans have limited short-term memory, it is necessary to provide knowledge in a "good order", and this is very hard for the author.
    - [[Writing is one-dimensional]]

> [nishio](https://twitter.com/nishio/status/1643813862008033283) Rather, it is better to identify "what information is missing" based on users' questions and add it, and it is important to create a system to do so. It is important to build a system to do that.

2023-11-10
> [tokoroten](https://twitter.com/tokoroten/status/1722613867459870989) I've been able to make a custom model by feeding PDF into ChatGPT,
>  "A book is an additional data set to the LLM" feels like a definite future.
>
>  E-book services that can work with LLMs are going to be the next dominant e-book service.
>  The age when a stack of books will be eaten up by LLMs, which will then be useful.

> [unnonouno](https://twitter.com/unnonouno/status/1722628474937172341) Conversely, the writing process is going to be data creation that feeds the LLM (it no longer even needs to be in Japanese). It's going to be a custom LLM creation service, not publishing.

> [tokoroten](https://x.com/tokoroten/status/1722638049883082908) Books are inefficiently efficient input to AI because information is forced to be one-dimensional for human readability.
>  I have a feeling that the next generation will be strong in those who can create information in a data structure that is convenient for AI.
>
>  (From Nishio's conversation log from April or so) [[Easier to write for LLM than to write for humans.]]

> [nishio](https://twitter.com/nishio/status/1722775665345523735) I'll write the date and related links later w

> [nishio](https://twitter.com/nishio/status/1722778725996175712) Just yesterday we were talking about connecting FAQs to LLMs, and these FAQs are not books, "[[a]] format for transferring knowledge" and will be used more widely as the search gets better. I'm sure they will be used more widely as search becomes better and more precise in answering questions.
- [[Cybozu Days 2023-11-09]]

> [nishio](https://twitter.com/nishio/status/1722779478685110539) When it comes to moving from books to FAQs, "What should I know first?" What will I get from reading this book? etc., and for those who want to read the book in a one-dimensional way, you can give them one "next question candidate" for each answer.


> [tokoroten](https://twitter.com/tokoroten/status/1722783854761771161) There are cases where what we call FAQs are really FAQs and cases where the line is drawn by FAQs, so the former will be LLM It will be absorbed, but I don't think all of it will be incorporated because of the latter feature.
>  [https://tokoroten.medium.com/情報ⅰBooks-Uncollected](https://tokoroten.medium.com/情報ⅰBooks-Uncollected) Manuscript Offerings-The%EF%BC%92-c5c48fd04a69
>  ![image](https://pbs.twimg.com/media/F-iOovuaEAAyiqR?format=png&name=small#.png) ![image](https://pbs.twimg.com/media/F-iOs6SbMAAdGZ9?format=png&name=900x900#.png)

> [nishio](https://twitter.com/nishio/status/1722785628868530357) Maybe the latter will display a source label such as "official information" or "community" and the recipient will be able to make a decision based on that?

> [nishio](https://twitter.com/nishio/status/1722788318386204728) Also, there was a discussion about what to generate in the "G" part of RAG, and many people try to create "answers" that propagate "truth", but I think that is a plot evil!  I prefer to generate "opinions" like "I thought this article might be useful in resolving your questions in terms of <[[summary based on user interest]]>."
- [[Generating Opinions]]

---
This page is auto-translated from [/nishio/人間のために書くよりLLMのために書く方が楽](https://scrapbox.io/nishio/人間のために書くよりLLMのために書く方が楽) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.