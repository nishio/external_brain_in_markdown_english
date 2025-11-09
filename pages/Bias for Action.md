---
title: "Bias for Action"
---


<img src='https://scrapbox.io/api/pages/nishio-en/GPT5/icon' alt='GPT5.icon' height="19.5"/>
Bias for Action
- Definition: an attitude of moving small and fast despite uncertainty. One of Amazon's Leadership Principles. ([amazon.jobs](https://www.amazon.jobs/content/our-workplace/leadership-principles?utm_source=chatgpt.com))
- Aim: Speed brings the learning curve forward and reduces lost opportunities (cost of waiting).

[[Two-way door]]／One-way door
- Framework (Bezos)
    - One-way door = Type 1: Irreversible (near irreversible) and high impact. Decide slowly, carefully, and after considering multiple perspectives.
    - Two-way door = Type 2: reversible and limited impact. Try it quickly in a lightweight process, revert if it doesn't work. ([SEC](https://www.sec.gov/Archives/edgar/data/1018724/000119312516530910/d168744dex991.htm?utm_source=chatgpt.com))

How to use in practice (shortest procedure)
1. determine reversibility
    - Low cost and quick return? → Two-way (immediate experiment)
    - Hard to put back in / Directly related to legal, brand, safety? → One-way (carefully)
2. estimate the scope of impact and waiting costs
    - Small impact x large cost of waiting → move first
    - High impact x Worth the wait → Gather additional information
3. two-way basic operation
    - Scope minimization → rollback procedure prepared → review criteria (KPI/failure conditions) with due dates determined and executed first
4. one-way basic operation
    - Comparison of alternatives/pre-mortem/stakeholder review/pilot operation (if possible) → decision making

Common mistakes
- Misidentification of Type 2 as Type 1 -> More procrastination and lost opportunities (corrected by Bias for Action). ([Amazon News](https://www.aboutamazon.com/news/company-news/2016-letter-to-shareholders?utm_source=chatgpt.com))
- Misidentification of Type 1 as Type 2 → unrecoverable damage (stricter Two-way determination). ([SEC](https://www.sec.gov/Archives/edgar/data/1018724/000119312516530910/d168744dex991.htm?utm_source=chatgpt.com))

Specific examples in software/research
- Two-way examples: UI wording changes, tweaking ranking weights, AB testing, small internal tool implementation (clear rollback possible).
- One-way examples: license change, revision of fee structure/contract terms, migration with data deletion, infrastructure change that leads to long-term lock-in.

summary
- Bias for Action is a "move first" attitude, and Two-way door is a "yardstick to identify situations in which you can move first.
- Classify first by reversibility x impact x cost to wait, Type 2 quickly, Type 1 carefully--this is the shortest operational rule. ([amazon.jobs](https://www.amazon.jobs/content/our-workplace/leadership-principles?utm_source=chatgpt.com))

---
This page is auto-translated from [/nishio/Bias for Action](https://scrapbox.io/nishio/Bias for Action) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.