---
title: "Relationship between LLM and Plurality"
---

2023-05-19
Relationship between LLM and Plurality
- LT at [LLM Meetup Tokyo 2
    - Since I have been focusing on Plurality-related issues for the past month ([[Plurality Tokyo]] - [[Manazuru 2023-05-13]]), I would like to talk about the relationship between LLM and Plurality.

What is [[Plurality]]?
- The concept proposed by [[Audrey Tang]], Minister of Digital Agency of Taiwan, et al.
- Concerns that linking AI to government will increase the power of government
- We need to consider using AI to make the people more powerful to balance the situation.
- This direction is called "Plurality" using "Plural (plural)" as a synonym for "Singular (singular)" in the "Singularity" that is supposed to be brought about by AI.

Technical Components of Plurality
- There are several, but it's impossible for LT to explain them all, so I'll just mention one.
    - [[broad listening]] :
    - > Enables "broad listening," where millions of people can hear the essence extracted from the distribution of opinions of their peers, and can enhance democratic [[careful deliberation]] on a large scale.
- For example, if you have a decent discussion with 100 people on Twitter, if you wrote 1 tweet your opinion, of course you should read 99 tweets
    - Are you doing this? You're not doing it.
    - Why aren't we doing it? Because it's too much of a burden for flesh and blood.
    - Then let's support that with digital technology!

concrete implementation
- Often used as a component [[Polis]].
    - Lower the burden of "listening to many people's opinions" by clustering "people with similar opinions."
    - This Polis does not use LLM.
- [[Stanford Online Deliberation Platform]] is doing [Moderation Automation
    - Natural language processing is the future
- This is an area where there could be interesting developments using LLM in the future!

Circumstances unique to Japan
    - [[Broad Listening is Important in Japan, Where Air Rules]]
- [[Erin Meyer]]'s research shows that Japanese culture is such that "it is better for everyone to build consensus than for the boss of an organization to make top-down decisions."
    - Many want to "involve themselves in the decision-making process."
    - But many people don't speak for themselves.
    - You don't speak your mind, but you want your opinion to be taken into account.
        - Why Japanese People!
- Need to design a system that takes care of this Japanese cultural background.
    - ![image](https://gyazo.com/3b5e969822d2773f6a36009707b6c2f6/thumb/1000)
    - Each person's statement is first heard by the LLM
    - Anonymize and summarize it and feed it back to everyone.
    - (If I had more time, I would have liked to get to the point of actually building and demonstrating this, but I couldn't make it in time.)

---
This page is auto-translated from [/nishio/LLMとPluralityの関係](https://scrapbox.io/nishio/LLMとPluralityの関係) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.