---
title: "pContinuousTranslation2023-06-01"
---

[[pContinuousTranslation]]
![image](https://gyazo.com/5996dee7830c6ef1091d12bbde40fa2c/thumb/1000)
> [nishio](https://twitter.com/nishio/status/1663946852985872384) I'm considering whether to improve the current DeepL-based automatic translation system for Scrapbox or switch to a GPT-based system.

> [nishio](https://twitter.com/nishio/status/1663949478041362435) DeepL based method Pros
>  ・There is a glossary function, so that you can control the way certain words go to certain translations.
>  ・Implemented a mechanism to replace existing mistranslations without using the API by checking the occurrence points
>  ・If you work hard, you can have it translated while maintaining its structure (via XML)
>  Cons
>  ・Hard work is troublesome

> [nishio](https://twitter.com/nishio/status/1663950355120676864) GPT-based method Pros
>  ・Seems great (bluff)
>  ・ Actually, 3.5 would be cheap.
>  ・Translation can be adjusted simply by indicating in natural language
>  Cons


> [nishio](https://twitter.com/nishio/status/1663950546305441793) The theory is that if you have to work hard either way, you might as well work hard on GPT.
>
>  The theory is that the people in DeepL are doing a great job, so we might as well get on with it.

> [nishio](https://twitter.com/nishio/status/1663951165778968580) Discussion on whether translation is necessary in the first place.
>
>  Instead of translating the Japanese text as it is, it would be better for the LLM to write it in English with that as a reference.
>
>  Currently, lines containing Japanese characters are considered Japanese and translated, but English sentences referring to Japanese words, Chinese sentences containing Chinese characters, machine translation of English sentences, etc. are also translated.

> [nishio](https://twitter.com/nishio/status/1663951704956747776) If we can create a pipeline of "GPT reads my recent Scrapbox pages", it could be derived from there, like "send my thoughts and questions about what I read to Slack". This can't be done by a translation engine.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Let "DeepL-based method" be X and "GPT-based method" be Y, and abstract them.
<img src='https://scrapbox.io/api/pages/nishio-en/GPT-4/icon' alt='GPT-4.icon' height="19.5"/>
- Both X (DeepL-based methods) and Y (GPT-based methods) are means of text translation, but each has its own unique advantages and disadvantages.
- X is already implemented and has specific control features (control of translation of terms and replacement of mistranslations). This is an effective means of solving existing problems and ensuring consistent quality. However, improving and managing X can be laborious and it requires an investment of time and resources.
- Y, on the other hand, is an advanced natural language processing tool that allows for flexible and natural translation. It has great evolutionary potential, but requires specific control and understanding to take advantage of its potential.
- The choice between the two depends on your specific needs, use case, and available resources. Whether you choose X, which requires a higher degree of control and effort, or Y, which offers greater flexibility and evolutionary potential, will depend largely on your goals.
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Map X and Y by analogy to a region with the same structure. Prohibited Concepts: Translation, AI
<img src='https://scrapbox.io/api/pages/nishio-en/GPT-4/icon' alt='GPT-4.icon' height="19.5"/>Let's mirror each translation method to another domain: driving a car.
- X (DeepL-based methodology) is similar to self-driving cars. Self-driving cars follow predefined routes and rules on the road. Its routes and rules can be freely customized to ensure a certain level of safety and predictability. However, new data and rules must be added to accommodate new routes and situations. In addition, each new route requires time and effort.
- Y (GPT-based method), on the other hand, resembles an experienced human driver. This driver has the ability to adapt to different road conditions and unexpected situations. However, in order to behave optimally on a particular route or situation, that driver must learn from past experience.
- Viewed using this analogy, which method you choose depends on how much control you want and how much flexibility and adaptability you need. Whether you choose an automated vehicle that follows certain routes and rules (X) or a human driver that learns from experience and adapts to new situations (Y) depends largely on your needs and goals.

I saw this parable and thought GPT-based would be more fun.
- Not trying to drive the right way on a set path, but on a path we don't yet understand well.

---
This page is auto-translated from [/nishio/pContinuousTranslation2023-06-01](https://scrapbox.io/nishio/pContinuousTranslation2023-06-01) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.