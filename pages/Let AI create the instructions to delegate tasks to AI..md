---
title: "Let AI create the instructions to delegate tasks to AI."
---

- [[AI Task Management]]
prompt: look at the following to identify tasks that could be delegated to AI, choose 3 of the smaller ones, and create a prompt to delegate to AI

<img src='https://scrapbox.io/api/pages/nishio-en/o3-mini-high/icon' alt='o3-mini-high.icon' height="19.5"/>
1. summarize yesterday's conversation in text
Task Overview
- Extract key discussion points and decisions from yesterday's conversation log and briefly summarize them in chronological order.

Prompt Example
> Read the following conversation log and summarize the main discussion points, decisions, and key speaker comments in brief sentences in chronological order.
>  [Input
>  (*Paste text of conversation log here)

2. create random page extraction code from Scrapbox export JSON
Task Overview
Create code (e.g. Python) that reads the JSON file exported from Scrapbox and randomly selects one page from it to output its contents.

Prompt Example
> Create a Python script that reads the Scrapbox export JSON file and randomly selects one page to display its title and contents. Please use only the standard library and make sure the code is easy to understand and commented.

3. review of interview audio transcriptions
Task Overview
Check the text of interviews that have already been transcribed and correct unnatural expressions, typographical errors, and inconsistencies in context to make the text more readable and well-organized.
> Please read the interview transcription text below and correct any unnatural expressions, typos, or inconsistencies in context. Please rewrite the text to make it more readable and accurate.
>  [Input
>  (*Paste transcribed text here)


---
This page is auto-translated from [/nishio/タスクをAIに任せる指示をAIに作らせる](https://scrapbox.io/nishio/タスクをAIに任せる指示をAIに作らせる) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.