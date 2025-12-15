---
title: "The Relationship Between LLM and Plurality"
---

2023-05-19  
The Relationship Between LLM and Plurality  
- Presented at [[LLM Meetup Tokyo 2]]  
    - Having focused on Plurality-related matters over the past month ([[Plurality Tokyo]] to [[Manazuru 2023-05-13]]), I will discuss the relationship between LLM and Plurality.

What is [[Plurality]]?  
- A concept proposed by [[Audrey Tang]], Minister of Digital Affairs in Taiwan, and others  
- There is a concern that the power of the government could increase if AI and government become intertwined  
- To maintain balance, we must consider using AI to empower the populace  
- This direction is called "Plurality," using the term "Plural" as the antonym to "Singular" from "Singularity," which AI is said to bring about

Technical Components of Plurality  
- There are several, but explaining all in a short talk is impossible, so I will cover just one  
- [[Broad Listening]]:  
    - > Enables "broad listening," allowing millions of people to hear the essence extracted from the distribution of peer opinions, thereby enhancing large-scale democratic [[deliberation]].  
- For example, when having a proper discussion with 100 people on Twitter, if you post one tweet with your opinion, you should naturally read 99 tweets  
    - Are you doing this? No, you're not  
    - Why not? Because it's burdensome for a human being  
    - So let's support this with digital technology!

Specific Implementations  
- [[Polis]] is often used as a component  
    - Reduces the burden of "listening to many people's opinions" by clustering "people with similar opinions"  
    - This Polis does not use LLM  
- [[Stanford Online Deliberation Platform]] is working on [[automating moderation]]  
    - Natural language processing is still to come  
- A field where interesting developments are expected by utilizing LLM in the future!

Japan's Unique Circumstances  
- [[Broad Listening is Important in Japan, Where Air Rules]]  
- According to [[Erin Meyer]]'s research, Japanese culture favors consensus-building over top-down decision-making by the organization's boss  
    - Many people want to be involved in the decision-making process  
    - However, many do not express their opinions  
    - They want their opinions to be understood even if they don't express them  
        - Why Japanese People! That's strange!  
- A system design that considers this cultural background in Japan is necessary  
    - ![image](https://gyazo.com/3b5e969822d2773f6a36009707b6c2f6/thumb/1000)  
    - LLM first listens to each person's statement  
    - It then anonymizes and summarizes it for feedback to everyone  
    - (If time allowed, I wanted to actually create and demo this, but I couldn't make it in time)

---
This page is a high-quality translation from [/nishio/LLMとPluralityの関係](https://scrapbox.io/nishio/LLMとPluralityの関係). The original content is maintained by NISHIO Hirokazu.