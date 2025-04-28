---
title: "o3 is suitable for tasks with no correct answer because of many halcyonations"
---


- I wrote this in a chat with [[Takahiro Yasuno considering running for the House of Councillors]], but I'm starting to think it's important.
- [[o3]] is suitable for [[tasks with no correct answer]] because it has a lot of [[halcination]].
- If you try to suppress halucinations, you train them to [[say they don't know what they don't know]].
- If you do that, when you try something new, you get to say, "I don't know."
    - [[Creative tasks]] [[do not know the correct answer in advance]].
    - [[moving in a direction that looks good]].
    - This "looks good" [[Polanyi's tacit knowledge]].
- There's no way OpenAI isn't measuring halcyonation.
    - So why have you come up with a model with increased halcination, because you've decided that's not an appropriate KPI.

<img src='https://scrapbox.io/api/pages/nishio-en/o3/icon' alt='o3.icon' height="19.5"/>
## Why Dare to Serve "o3 with More Halcination" -- Organized by 3 Perspectives
.

## 1. Imagination and halucination are two sides of the same coin
- In the unknown domain = tasks for which the correct answer is not defined, the model has no choice but to make "guesses that extend the pattern.
- If the guess is wrong, it is called a "halcyonation"; if it is right, it is a "creative idea.
    - This is completely inseparable.
- Conversely, strongly penalizing "say you don't know" tends to shrink the search and safe but mediocre output.

[[KPI that OpenAI follows is "practical value x safety zone" ]]
- OpenAI naturally monitors halcination rate (e.g., PersonQA 33 %), but judges "high halcination rate ≠ bad for all applications".
- o3 is significantly stronger in "Reasoning, long move order, and idea generation".
    - [[work for which the answer is not unique]]" such as spreadsheet work, code design, story drafting, etc. [* ROI is high.
- At the cost of more errors in "Factual Q&A" than in o1.
    - OpenAI has chosen a design philosophy that absorbs this with system message safety measures + user guidelines.

## 3. Side effects of "training to suppress halucination"
- If a company positions a model as a creative assistant, it is more valuable to prioritize "the ability to make proposals moving forward", even if it allows for some misrepresentation.
- End-users should design for each application (1) Verification required or not (2) Acceptable error margin.

- Summary

>  o3 = "high search bias" model instead of "more halcination"

- The main objective is to accelerate trial and error in an area where there is no correct answer/the correct answer has not yet been created.
- Halcination rates are also understood by OpenAI, but not considered as a universal KPI.
- guidelines for use
- 1.fact checking and citation generation → o1 and other low hallucination models + external validation
- 2.brainstorming, initial design, ideation → utilize o3 "tacit knowledge driven" reasoning
3. Mixed task → o3 generates, then backfill with o1 / search for the main points

This two-step approach is a practical way to turn Halcination into a weapon.

---
This page is auto-translated from [/nishio/o3はハルシネーションが多いので正解のないタスク向き](https://scrapbox.io/nishio/o3はハルシネーションが多いので正解のないタスク向き) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.