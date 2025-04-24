---
title: "AI Task Management 2025-01-27"
---

2025-01-27
- [[AI Task Management System]] Reflecting on the experience of creating and experimenting with the system for about 3 weeks, I would like to reiterate the language.

- When we say [[AI Task Management]] or [[AI Project Management]], we tend to associate it with [[Task Management]] or [[Project Management]] that already exists.
- But what's already working the way it's supposed to work doesn't need to be replaced.
- I think we need to address areas where good methods don't exist now and new needs are emerging.
- 1: [[Exploratory tasks]] that do not have a clear structure have been difficult to manage
    - This can be better managed by LLMs, who have a wider context range than humans.
    - Specifically, extract tasks from unstructured data such as ChatGPT's [[Advanced Voice]] or conversation logs with AI agents in the form of JSON objects with format definitions
        - [format definition](https://github.com/nishio/ai_project_manager/blob/main/docs/task_format.md)
    - Currently, backlog.json with 108 tasks is generated in this way, and AI can read it and do various things with it.
            - [[AI Task Management System 2025-01-08]]
        - Discussion by o1 Pro: [[Weekly 2025-01-25~2025-01-31#67948e31aff09e0000051233]]
    - Exploratory tasks are not clear in advance what they are to do.
        - After doing a lot of things with unclear importance, the knowledge gained from them allows us to verbalize "why it is important" after the fact.
- 2: As AI agents become more prevalent, many people will need to do "the job of managing 'many workers working in parallel who are not themselves'".
    - I think this area needs to be supported.
            - [[Try Devin.ai 2025-01]] and felt that way, it's hard for me without support.
    - A [[PMBOK]]-like knowledge system has been developed to manage human workers here, and much of it can be appropriated.
    - On the other hand, the fact that the worker is an AI agent [I can see the thought process.
        - Up until now, when humans have failed, they have said things like, "Let's improve the system instead of blaming humans.
        - but for AI agents, it is possible to go back to the logs after a failure and observe "why it failed".
            - For example, "I'm not reading the documents I was expecting to read, I'm reading the old ones I found by grepping the project.
        - AI agents become workers, making it rather easy to improve work processes.

prev  [[AI Task Management 2025-01-26]]


Development Memo
It's been a bit of a mess since the redesign, but we're getting the data right.
![image](https://gyazo.com/28d2445a28dd8a0112102013d9351b73/thumb/1000)
But if I validate immediately after acquisition and get an error, there is something wrong with the front part.

:

```
$ timestamp=$(date +%s) && git  checkout -b devin/$timestamp-fix-task-ids && source venv/bin/activate
Switched to a new branch 'devin/1737934684-fix-task-ids'
```

I'm reading all 1182 lines of backlog.json four times after this.
- I'd like a way to fix this without reading the whole thing here.

Ah, I see, you completed the correction correctly, but then cloned it separately by mistake.

memo
- You have to decide in advance how you're going to manage the tasks that come to mind while you're fiddling with your task management tool.
    - You can write it on a paper note or talk to ChatGPT.

---
This page is auto-translated from [/nishio/AIタスク管理2025-01-27](https://scrapbox.io/nishio/AIタスク管理2025-01-27) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.