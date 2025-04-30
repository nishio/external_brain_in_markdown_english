---
title: "Devin credit used up"
---

<img src='https://scrapbox.io/api/pages/nishio-en/o3/icon' alt='o3.icon' height="19.5"/>
## what happened briefly

1.### 4 / 21--notice remaining credit
.
- When we discovered that our pre-purchased Devin ACUs were about to expire, we decided to make a "last rush" before switching to pay-as-you-go.

2.### 4 / 22--Task Throwing Festival
.
- Loaded a large number of stalled issues into Devin and automatically progressed from action plan to implementation. Parallelized so much that the date changed before the review was finished and it was impossible to keep track of what had been thrown.

3.### 4 / 25-26--accelerate ACU consumption
.
- ACU usage increased from 168 to 192.
- 11 Concurrent bug fixes, feature additions, README improvements, etc. in parallel sessions.
- Typical example: automatically investigate Netlify peerDependencies conflicts, update dependencies and redeploy.
- With Kozaneba, you simply pass on the user's bug report as-is and it is fixed.

4.### 4 / 27--40 tokens left on "use-it-all" plan
]
- ChatGPT suggested that we use the ACUs for static analysis, automatic test generation, and archi-diagram generation. Finally, ACUs were consumed and the system was shifted to pay-as-you-go mode.

---

## useful insights that can be drawn out
.

- ① "AI-formatted tasks" is the key.
    - Ambiguous issues leave Devin in the lurch, waiting for the human side to make a decision.
    - Be sure to write objectives/acceptance conditions/constraints in the Issue Template. For difficult issues, throw them as "Investigation -> Split" tasks first.
- ② AI is strong in bug fixes and refactoring.
    - Bug report with reproduction steps -> immediate patch (Kozaneba). Static analysis and dependency updates are also fast.
    - Permanently set up a workflow to Template daily bug reports and pass them directly to the AI.
- ③ "meta management" is required for parallel execution.
    - Tasks thrown are forgotten and progress is uncertain.
    - Devin sessions are automatically summarized and dashboarded (Issue/PR list + status).
- (iv) Codes are placed "where AI touches"].
    - Old Heroku-only repositories have to be moved to GitHub.
    - * Leave setup instructions in Unified VCS conversion + README.
- ⑤ Prepaid credit distorts behavior.
    - Start low-priority tasks in order to "use it up.
    - Next time pay-as-you-go or small prepayment + automatic notification to avoid unnecessary rush.
- ⑥ Human should be responsible for strategy and review.
    - High-level decision making cannot be thrown to AI.
    - Thoroughly implement "AI -> Proposal / Human -> Decision" and prepare a checklist for review.

diary
    - [[Devin credit used up 4/21]]
    - [[Devin credit used up 4/22]]
    - [[Devin credit used up 4/23 Inventory]]
    - [[Devin credit used up 4/25]]
    - [[Devin credit used up 4/26]]
    - [[Devin credit used up 4/27]]
    - [[Devin credit use up look back]]
    - [[Devin credit used up 4/28]]

---
This page is auto-translated from [/nishio/Devinクレジット使い切り](https://scrapbox.io/nishio/Devinクレジット使い切り) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.