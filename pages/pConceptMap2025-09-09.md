---
title: "pConceptMap2025-09-09"
---

[[pConceptMap]]
- prev [[pConceptMap2025-09-08]]

I had been experimenting with a script in a plurality repo, but I decided that it would be better to use an independent repo for release, like Vercel, so I cleaned up the mess.

Currently, prototypes are created by replacing HTML files, but we want to create them with something like React to make the UI improvement cycle more efficient.
I want to eventually export and release static HTML.

Try git worktree

Improvements to prompts.py
- "tier": "core"|"supplementary"|"advanced" This should be deleted.
    - Create a tier by extracting different max_concepts in the future.
- Allowed relation types (choose one): {relation_types} also remove this limitation
    - Relationships are expressed in short sentences that include the subject

![image](https://gyazo.com/4aaf806256e93599ddd0aab216d69c4f/thumb/1000)

Bug that parallelism is reset when clicking on a node after a parallel move.

The "relation" is now a sentence, but we would like to rename it to the field name "relation_description" and put a short expression of one word, or at most three words, in the "relation" field if possible. The reason for this is to display it as an edge label when drawing the graph.
- ![image](https://gyazo.com/5a35e5824f617395efe626282b8f4a61/thumb/1000)


It's not a good view if the quote contains `***`, but should I leave it to see where it appears?
- Is there a way to simply make the display part of the WebUI a Markdown component?

When you click on a relation label, it would be nice if information about that relation (citation, etc.) would appear below the node information that is currently displayed.
- ![image](https://gyazo.com/4db9e134e44528ef00c442379d158796/thumb/1000)

![image](https://gyazo.com/6ebed93497e9f913cbef78a985111263/thumb/1000)![image](https://gyazo.com/d781b407bbf1e940c69e757f2560c372/thumb/1000)


Let's make sure that concepts and relationships detailed in the cards are highlighted in the graph on the left.

![image](https://gyazo.com/3dc3063927860fb9d255496d51cf5637/thumb/1000)
![image](https://gyazo.com/3d98c29cec8322a89ab0b55f83a823a6/thumb/1000)

I'd love to get it into a state where others can touch it today.
- Maybe GitHub Actions to generate static and GitHub Pages.
- Well, once you do, you can do it manually.
    - And when I say manual, I mean AI hands.


I want to use this for a single book manuscript that has "multiple chapter files with multiple sections within them".
- I think simply displaying the whole thing would be impactful but not user friendly.
- Let's make a plan of what to do.


AI created a whole section integration on its own, but it still didn't work.
- ![image](https://gyazo.com/57627baef5a70a5bca517f02989ad084/thumb/1000)




When a node is dragged and released, it is pinned and its position is fixed.

It seems like a good idea to pass the graph to GPT5 to find the occurrence of keywords across chapters
- That is, important concepts that are discussed in multiple chapters.


There are patterns in the individual chapter graphs that are not consolidated.
- That it is not enough because 10 concepts are extracted out of the decision.
- Maybe we could do a separate one to help them find the concepts that connect the in-between.


It would be interesting to be able to extract references that cross chapters as well.

---
All data completed.
- $1


---
<img src='https://scrapbox.io/api/pages/nishio-en/Claude/icon' alt='Claude.icon' height="19.5"/>
⏺ Behavior during long chapter data processing
1. automatic truncation at 12,000 characters (pipeline.py:151, line 177)
- When sending to LLM, process only the first 12,000 characters in sec.text[:12000
- The rest of the text is ignored.

Critical Problem Found:.
1. 2-0-IT and Democracy The Enlarging Divide.md
- Section 9: 25,515 characters → 53% lost
2. 3-3-the lost road.md
- Section 10: 16,308 characters → 26% lost
More than half of the important content (in the case of 2-0) is not processed in these sections. Simple truncation by `sec.text[:12000]`.
The first time the text is used, context and important information may be lost.

I thought this was a great problem, but it's just a bunch of footnotes at the end of the page.<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>

---
Work to convert non-linked chapters into linkages
    - [[associative connection]] That's the one.

![image](https://gyazo.com/c653ec9244d36e22b270920d47a81f61/thumb/1000)
It's done.
![image](https://gyazo.com/718eb1605c505b864832f96b8c08df68/thumb/1000)
It's been successfully repaired.

Version not an isolated point
![image](https://gyazo.com/441786e1b1e7738181fc1c2fc6979b63/thumb/1000)
![image](https://gyazo.com/6c98c1a69569b3314f9bbe6e22cd4b3a/thumb/1000)
I see, you inserted "online version" between "get the latest version" and "non-linear reading and hyperlinks".

By the way, I've created a tool to generate a prompt with all the necessary information, and I'm throwing it to ChatGPT 5 Thinking.

![image](https://gyazo.com/e94d9c5d52ab01e3de403b51a4ae262a/thumb/1000)

I wonder if we can do this with the 5-mini.
- But I don't think it's necessary to implement it because I can just throw a few cases as I look at them.
- "The 4-3 bridging concept is 'checks'."
    - interesting

![image](https://gyazo.com/d3b9bb1df51aba6afb75bac8bd081333/thumb/1000)
- Add SNS node and connect

![image](https://gyazo.com/e252d0cfd47f2a1c1e8339498328614a/thumb/1000)
- I'm looking forward to seeing how this works out.
- > The proposal is to add a minimum of 3 bridging concepts to fill the lack of linkage, and all nodes are merged into one main linkage component with 12 edges.
- ![image](https://gyazo.com/82903fdbe4b6d8d2b30b2b95b7e1a143/thumb/1000)
- Connected!

[[pConceptMap2025-09-10]]

---
This page is auto-translated from [/nishio/pConceptMap2025-09-09](https://scrapbox.io/nishio/pConceptMap2025-09-09) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.