---
title: "pConceptMap2025-09-08"
---

from [[A Framework for Constructing Concept Maps from E-Books Using Large Language Models: Challenges and Future Directions]]
[[pConceptMap]]2025-09-08
- [[Concept Map]]

memo
[https://chatgpt.com/c/68ba96f1-2650-8320-84a6-33bb3f7838ae](https://chatgpt.com/c/68ba96f1-2650-8320-84a6-33bb3f7838ae)

> 4 stages: (1) sectioning → (2) concept extraction → (3) relationship identification → (4) integration
- Labels for extracted concepts
- Identification of the relationship between them
- This is the trend.[[Keichobot]]にも関係しそうだ<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>

---
Summary of experimental results:
📊 Generated concepts (5):
- globalization - core
- digital technology - core
- democracy - core
- plurality - core
- collaboration - supplementary

🔗 Relationships between concepts (4):
- globalization → digital_technology (prerequisite_of, 0.90)
- democracy ← collaboration (part_of, 0.85)
- digital_technology → plurality (example_of, 0.80)
- democracy ↔ globalization (contrasts_with, 0.75)

---
I understood the approximate flow.
- First, "keywords that seem important" are extracted from the given document,
- Then give that keyword list and a set of documents to extract the "relationships".


cost consideration
- Now gpt-4o-mini
- > The fee for developers is 15 cents per million input tokens and 60 cents per million output tokens (equivalent to about 2500 pages in a standard book).... . ChatGPT will allow Free, Plus, and Team users to access GPT-4o mini, which replaces GPT-3.5, starting today.
    - [https://openai.com/ja-JP/index/gpt-4o-mini-advancing-cost-efficient-intelligence/](https://openai.com/ja-JP/index/gpt-4o-mini-advancing-cost-efficient-intelligence/)
- [https://openai.com/ja-JP/api/pricing/](https://openai.com/ja-JP/api/pricing/)
    - GPT-5, mini, nano
        - $10, $2, $0.4 in output

GPT-5-mini vs. other model comparison
Features of the 🏆 GPT-5-mini
📊 Degree of detail of concept:.
- More detailed and precise concept definition
- Extract even the finest elements: **⿻ (Unicode symbol)**.
- Compound understanding combining Japanese and symbols
🔗 Accuracy of the relationship:.
- Six relationships are extracted (other models have about four)
- High confidence (0.90-0.95)
- Interrelationships are also captured (uses ↔ example_of).

![image](https://gyazo.com/851cbee2aebdb5d10fc28abccbdef89a/thumb/1000)
I'd like to synthesize the two-way arrows because it's hard to see them overlapping.
- It's a pre-LLM idea to extract a relationship like part_of in the first place, let the relationship be explained in words too.
- [[Do not symbolize the relationship]].

- [[Text-based relationship extraction]]
- [[relationship is meaning and vice versa]]

next [[pConceptMap2025-09-09]]

---
This page is auto-translated from [/nishio/pConceptMap2025-09-08](https://scrapbox.io/nishio/pConceptMap2025-09-08) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.