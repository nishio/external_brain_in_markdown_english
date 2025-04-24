---
title: "SELFGOAL x Power Prompt"
---

> [hokazuya](https://x.com/hokazuya/status/1805920687686914432) [[SELFGOAL x Power prompt]]
>  I crossed the Power prompt with the SELFGOAL prompt I created based on the paper, and after only a few additional instructions, a VSCode-like WebUI was completed.
>
>  Golden prompts that are quite precise and automatically advanced operations. I wrote the prompt based on the paper.
>
>  AI will automatically create a result that is as close to the Main Goal as possible by letting AI itself decompose the Goal into SubGoals, a concept similar to GoalSeak, but utilizing AI's own strengths in task decomposition. In principle, no steps are required, and if it stops in the middle of a task, it will only add some supplementary information to encourage subsequent steps.
>
>   [[(computer) prompt]]
>  You are an advanced AI assistant.
>
>  #Main goal:
>  Your task is to develop a rich web-based IDE similar to VSCode. This IDE should provide a robust development environment that allows efficient coding, debugging, and collaboration directly in the browser. Please agree to work in favor of the project based closely on the following work steps
>
>  # Work Steps
>  1. break down the main goal into detailed and actionable sub-goals.
>  2. prepare detailed and practical sub-goals to help achieve the main goal
>  3. Implement the subgoals in order from the first of the decomposed subgoals to achieve the main goal.
>  4. You are an advanced AI, so every time you implement one of the Sub Goals, the result looks like a 60 to you; consider a corrective action plan to make it a 100.
>  5. After making corrections based on the correction policy, start the next SUB GOAL task.
>  6. After all sub-goals have been implemented without omission, comprehensively check whether the main goal has been achieved.
>  7. after these steps are completed, announce the completion to the user. The user is not asked to confirm the completion of the process, but to proceed on his/her own.

It will not check with the user until completion, but will proceed on its own." is interesting.


---
This page is auto-translated from [/nishio/SELFGOAL×Powerプロンプト](https://scrapbox.io/nishio/SELFGOAL×Powerプロンプト) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.