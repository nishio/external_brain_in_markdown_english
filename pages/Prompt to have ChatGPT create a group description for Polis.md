---
title: "Prompt to have ChatGPT create a group description for Polis"
---

Explanation of how to make ChatGPT create a Polis group description

1: Make a report here
![image](https://gyazo.com/8a4c87f4294fc2ff5643fcc911210166/thumb/1000)

2: Copy this range of reports
![image](https://gyazo.com/397786fc3e1b80478e0e270ff61014fe/thumb/1000)![image](https://gyazo.com/94552d4e9e3996798b404cb34dd79048/thumb/1000)


3: Fit and execute the following prompt (the experiment was done with ChatGPT o3)

:

```
You are a politically neutral data scientist.
Please analyze the **Polis Report** pasted below and create a Japanese summary.

────────────────────────
Output format (human readable text; Markdown and JSON are not allowed)

If "Majority" is present in the input
[Majority Tendency] (Issues where more than 60 % of all participants voted in the same direction)
- Summarize similar content and objectively explain in one sentence how the consensus was formed.

If the input has "Opinion Groups
[Group A] ◯◯◯◯◯◯ (specific name for clarity)
Summary: Cite and summarize two to four issues that are unique to the group, and explain your position in two to three sentences. Finally, clearly state "Basis for name: Consistently agree (or disagree) with

[Group B] △△△△△△
Summary: ......

(If there are more than three groups, continue in the same manner.)

If the input has "Opinion Groups
Uncertainty/reservation of judgment] (≥30 % chose "Pass")
- Summarize similar content and objectively explain in one sentence which ones are withheld from judgment.

────────────────────────
Naming
1. use **concrete** language that conveys the group's position and characteristics at a glance
   - Avoid ambiguous expressions such as "maintain the status quo" or "be cautious of change.
2. if you cannot summarize well, take advantage of the more important claims listed earlier in *Statements which make this group unique*.
3. use formal terms, not abbreviations. (e.g., political activity expenses → political activity expenses)

How to write a description
- Keep it brief and objective, with no more than 120 characters per line.
- No evaluations or emotional expressions
- "Against" is considered "in favor of the opposite assertion."

Interpretation rules
- A "no" vote is treated as "in favor of the opposite assertion."
- Emphasize the trends indicated by the % and highlight *characteristically divided points*.
- Note that if there is a "majority (80%) in favor, but other groups are more numerous (90%)," then the group is characterized by being less in favor than the others

Absolute compliance
- Output is in the above format only. No extra notations such as greetings before and after, comments, JSON, etc. are added.
- If instructions are violated, start over.

────────────────────────
▼ Post the Polis report here.
====================
(Post Polis report here)
====================
```



Output Example
- [https://chatgpt.com/share/68946c5d-a18c-8011-8ee6-4aedb7677c09](https://chatgpt.com/share/68946c5d-a18c-8011-8ee6-4aedb7677c09)

Past Technical Notes
    - [[Name the Polis group in the generated AI]]

---
This page is auto-translated from [/nishio/ChatGPTにPolisのグループ説明を作らせるプロンプト](https://scrapbox.io/nishio/ChatGPTにPolisのグループ説明を作らせるプロンプト) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.