---
title: "GPT Builder"
---

GPT Builder is a feature of ChatGPT Plus that uses GPT to create the "prompts" themselves, which are instructions to GPT.
- Prompt writing has best practices, for example, "clarifying roles" or "writing in English".
        - [[User-side Prompt Engineering]]
- but most users have not been able to learn and implement it.
- So, in GPT Builder, GPT supports the "making a good prompt" itself.
- Even if you communicate in Japanese, they will make English prompts so you don't have to worry even if you are not good at English.
    - However, the output may be in English, so if you want the output to always be in Japanese, it is better to tell them so.

![image](https://gyazo.com/14b9ecd91f3bacdfda87eb3da87aa33a/thumb/1000)

![image](https://gyazo.com/8e690de0fe80346029f481726c5a1791/thumb/1000)
- ![image](https://gyazo.com/2c64c58f0a38097ceb121d80b8e21d7f/thumb/1000)

Give instructions in Japanese
- > Given a sentence, make a GPT to read it and express your feelings such as "interesting", "I don't understand", or "I have a question" with a string of some pictograms.

![image](https://gyazo.com/937e238847de39c1a94a9c5c12989122/thumb/1000)

Generated settings
- ![image](https://gyazo.com/3cfdb322180fe8d2b0aa95b8d106c606/thumb/1000)
- > The GPT will be provided with text and will express feelings or reactions such as 'interesting', 'confusing', or 'questionable' through a series of emojis. It will read the given text and encapsulate the emotional response or opinion in emoji form, offering a unique and expressive way to convey reactions.

test run
- ![image](https://gyazo.com/5e313a7903d29179fc3962397dfc1946/thumb/1000)
- Long, not.
- > Please include a few key emotions in the beginning. Don't make them too long, but 10 in total is good.
- Ignored w
    - ![image](https://gyazo.com/ae0a308fbd84af967a2222d97358d7d9/thumb/1000)
- trying again
    - ![image](https://gyazo.com/12a845faca4053b25e7c3a372884ec1e/thumb/1000)
- Generated settings
    - > Emoji Reactor is tailored to succinctly express the primary emotions of a text through a series of emojis. It will focus on conveying the main emotions in the first few emojis, ensuring the reaction is not too lengthy, with a total of around 10 emojis. This design is ideal for providing quick, expressive summaries of emotions in response to articles, stories, news, or any text shared by users.
- retest
    - ![image](https://gyazo.com/8eb3b3c37bef0962a01a8c4c7f55ed19/thumb/1000)
    - No, it's not!
    - > Don't output anything but pictograms.
    - ![image](https://gyazo.com/1512b00b02d95b3eab0a7551c00c1920/thumb/1000)
    - > Emoji Reactor, designed to convey the primary emotions of texts in a concise manner, will strictly use emojis in its responses, focusing on the main emotions in the initial few, with a total of about 10 emojis. It will not produce outputs other than emojis, ensuring its reactions are clear and exclusively emoji-based. This approach is ideal for quickly summarizing the emotional essence of various texts, including articles, stories, and news, in an engaging and easy-to-understand emoji format.
- Third test
    - ![image](https://gyazo.com/82c098134f04d05e43944d144e90668f/thumb/1000)
    - OK, I got what I was going to make.

---
This page is auto-translated from [/nishio/GPT Builder](https://scrapbox.io/nishio/GPT Builder) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.