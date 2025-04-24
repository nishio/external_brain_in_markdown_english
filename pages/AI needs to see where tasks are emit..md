---
title: "AI needs to see where tasks are emit."
---

2025-02-09
- [AI Task Management System
prev:  [[Manage progress of short-term parallel work]]

The development started from the point that when Devin was given a lot of tasks to do in parallel, it was hard to have a lot of "waiting for human review" in parallel later on.
- Then mixed with [[exploratory task management]] talk
- These two requirements are quite different

I've tried a style of writing on a paper notepad and strike-through lines regarding "short-term parallel work progress management".
- And, okay, the problem is not progress management, but that these tasks are "not tracked unless a human puts them into a task management system."
- Once you request a task from [[Devin.ai]] in Slack, it should go into the task management system.
- The reason why I have been creating a ChatGPT-specific browser window since I started using ChatGPT in the first place is because by "new tab and talk to me," the tab is a representation of the task
    - [[Manage Unfinished Chats in tabs]].
    - But this was not good.
        - Session expired and redirected to login screen... type of thing started happening.
        - As the ease of use on the phone increases, more and more conversations are being initiated on the ChatGPT app from the phone, and that's getting lost.
        - That's why I've been posting more and more private chat links on this external brain.
            - My convenience outweighs the cost of one line of "unnecessary information" to the reader.
- [[OpenAI Deep Research]] came up, which took a few minutes and needed to be made into a task even more so!


If we push further and say that it would be better for AI to see human-human conversations as well, we approach "[[AI should be integrated with human input/output]]".


<img src='https://scrapbox.io/api/pages/nishio-en/o3-mini-high/icon' alt='o3-mini-high.icon' height="19.5"/>] The general approach is as follows
- Implementation of [event hooks
    - Establish hooks at the points where tasks are emitted and introduce a mechanism to notify the AI when they occur.
- Log collection and analysis
    - Collect logs during emit in real time so that AI can analyze them.
- Using [Message Queue
    - A mechanism will be employed whereby emit events are sent to a message queue and the AI monitors and processes that queue.
---
This page is auto-translated from [/nishio/タスクがemitされるところをAIが見る必要がある](https://scrapbox.io/nishio/タスクがemitされるところをAIが見る必要がある) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.