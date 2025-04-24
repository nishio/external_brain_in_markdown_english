---
title: "Talk to an AI with an orchestration layer."
---

> [nishio](https://x.com/nishio/status/1878660926154662108) It occurred to me that when you talk to an AI with an [[orchestration layer]], instead of "telling it what to do" like when you talk to a simple AI until now, you should tell it your "objective" and let it figure out how to achieve it. I think it's better to let the AI figure out how to achieve it on its own. (This is getting like whether or not to micromanage a human?)
> [cactaceae](https://x.com/cactaceae/status/1878661144472408307) I think the prompt guide for o1 talked about that.
> [nishio](https://x.com/nishio/status/1878665078477819947) Thanks for the info! I will take a look!

> [teramotodaiki](https://x.com/teramotodaiki/status/1878662902032539944) It's exactly like managing people, in the end it depends on how much discretion you can give Devin!
>  For example,
>  ・Is it OK to change behavior?
>  ・Is it OK to put in a new package?
>  ・Are pull requests allowed to be merged?
>  etc. If you can do whatever you want, just give them a goal, if you have a lot of constraints, you should give them a task.
> [nishio](https://x.com/nishio/status/1878665444275744815) As I was touching Devin, I was wondering if I should change the way I talk to ChatGPT o1 and when I talk to 4o. I'm going to read the Prompt Guide, because I heard that it actually says something like that.

The official documentation is micromanagement-esque.
- [Reasoning models - OpenAI API](https://platform.openai.com/docs/guides/reasoning/advice-on-prompting)
    1. give clear and specific instructions
        - It is important to avoid giving vague instructions to the model and to present specific and clear tasks. For example, specifying "Summarize the following 500-word technical article in 100 words or less" rather than "Summarize the following text" will produce more appropriate output.
    5. break complex tasks into steps
        - Complex problems or tasks should be broken down into smaller steps and instructions that are easier for the model to process. For example, step-by-step instructions such as "First analyze the data, then graph the results" will yield more accurate results.

I'm not sure if it's because o1 doesn't have an orchestration layer in the Devin sense of the word, but just a robust [[Chain of Thought]].
- So [[tool use]], such as Internet searches, is not possible.
- Devin is gaining capabilities in a different direction than o1

I was looking at [Best practices for prompt engineering with the OpenAI API | OpenAI Help Center [https://help.openai.com/en/articles/6654000-](https://help.openai.com/en/articles/6654000-) best-practices-for-prompt-engineering-with-the-openai-api], which was updated 3 months ago.
9. Use the [[Generate Anything feature]]

---
This page is auto-translated from [/nishio/オーケストレーション層の入ったAIと話す](https://scrapbox.io/nishio/オーケストレーション層の入ったAIと話す) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.