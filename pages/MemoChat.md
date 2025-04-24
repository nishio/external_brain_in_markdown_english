---
title: "MemoChat"
---

![image](https://gyazo.com/3ad5e109357b467a494879f9173f3c4d/thumb/1000)
[2308.08239 MemoChat: Tuning LLMs to Use Memos for Consistent Long-Range Open-Domain Conversation](https://arxiv.org/abs/2308.08239)

[https://aiboom.net/archives/54560](https://aiboom.net/archives/54560)

What are the characteristics of [[structured memory]] and how does it work?
- topic, summary, range

![image](https://gyazo.com/d8371d51aa8f07de692b6daa156188ad/thumb/1000)![image](https://gyazo.com/d97d7a77a685683c61a2bca627824693/thumb/1000)
looks done

for Scrapbox
:

```
You will be shown Conversation among people. Please read, memorize, and understand Task Conversation, then complete the task under the guidance of Task Introduction.
### Conversation

### Task
1 - Conclude all possible topics in the conversation with concise spans.
2- Determine the chat range of each topic. These ranges should be a set of non-intersecting, sequentially connected end-to-end intervals.
3 - Conclude a summary of each chat with brief sentences.
4 - Report topic, summary and range resutls in JSON format only with the assigned keys: 'topic', 'summary', 'startline'. Topic and summary should be in same language as the conversation.
For example, assuming an M-line conversation talks about 'banana' from line 1 to line N, then turns to talk about 'mango' from line N+1 to line M. Thus, its task result could be: [{'topic': 'banana', 'summary': 'user talks banana with bot.', 'startline': '...'}, {'topic': 'mango', 'summary': 'bot brings mango for user.', 'startline': '...'}].
```


---
This page is auto-translated from [/nishio/MemoChat](https://scrapbox.io/nishio/MemoChat) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.