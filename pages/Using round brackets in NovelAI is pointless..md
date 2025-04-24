---
title: "Using round brackets in NovelAI is pointless."
---

The drawing AI prompts have different syntax for different services and systems, but people don't understand them.
- For example, some people use the prompt with lots of round brackets for NovelAI.
- Token emphasis with round brackets is a feature of AUTOMATIC1111/stable-diffusion-webui, it does not work in NovelAI.
- NovelAI uses braces. Documentation: [Strengthening & Weakening Vectors - NovelAI Documentation](https://docs.novelai.net/image/strengthening-weakening.html)

To use a programming analogy, it's like "copying and pasting JavaScript code you find on the internet into Python code".
- In programming, it's almost always an error, so it's an opportunity to learn that "the action is futile."
- Unlike programming, drawing AI is error-free, so funny prompts get reproduced.

## Demonstration
.
model: NAI Curated, seed: 42, prompt: cat
![image](https://gyazo.com/76594a8a23249972f61bb4cfc3459330/thumb/1000)

If we multiply this prompt "cat" by $1.05^{20}$ with 20 braces, we get
{{{{{{{{{{{{{{{{{{{{cat}}}}}}}}}}}}}}}}}}}}
![image](https://gyazo.com/80ea2782877cca9c0bd753493b0c897b/thumb/1000)
So you've over-emphasized the token and deviated from the bounds of a decent painting.

On the other hand, if you do the same thing in round brackets, you get this
((((((((((((((((((((cat))))))))))))))))))))
![image](https://gyazo.com/ae3b0e5220ea114fa2c980ab8682a6c1/thumb/1000)
The round brackets are not interpreted as token-enforcing syntax, but simply as a string of prompts.
The brackets are tokens that have little meaning, so even if there are 20 of them attached, they do not affect the picture of a normal cat very much.


from [/villagepump/2022/11/04](https://scrapbox.io/villagepump/2022/11/04)
- >  [[code of elements]] は流出モデルで検証されているらしく()で描かれているのでこういうのの予感<img src='https://scrapbox.io/api/pages/villagepump/基素/icon' alt='/villagepump/基素.icon' height="19.5"/>

I see...so people in China can't connect to NovelAI's service? Are they being monitored by the authorities?
If you're using the spill model in AUTOMATIC1111/stable-diffusion-webui, it makes sense that the prompt would be in that syntax.


- [[Using round brackets in NovelAI is meaningless (experimental notes)]]
---
This page is auto-translated from [/nishio/NovelAIで丸括弧を使っても無意味](https://scrapbox.io/nishio/NovelAIで丸括弧を使っても無意味) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.