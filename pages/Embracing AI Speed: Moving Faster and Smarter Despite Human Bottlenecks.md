---
title: "Embracing AI Speed: Moving Faster and Smarter Despite Human Bottlenecks"
---

<img src='https://scrapbox.io/api/pages/nishio/GPT5/icon' alt='GPT5.icon' height="19.5"/>
In a world where AI operates overwhelmingly faster, we must abandon the premise of "understanding everything and controlling it by hand." Humans transition from being process supervisors to designers of objectives, constraints, and evaluation criteria. We delegate exploration, implementation, and self-recording (logs, summaries, version control) to AI, and assign testing and reviews to another AI. Humans periodically check only the output, deciding "what to consider a problem" and "what meaning to assign to each proposal." Even if we can't grasp the entire process, it's enough to control the entry and exit points and the rewind mechanism. While we can't change our slow pace, we don't need to slow down the whole system because of it. Although our slowness is a bottleneck, using it as a filter can actually make the whole system move faster and smarter than before.

![image](https://gyazo.com/6068456f18d27c4f25e7263deab8e526/thumb/1000)
- A: Before AI, human speed was slow, allowing a broader range of understanding
- B: With AI, the speed of human-AI pairs increased but still remained within human comprehension
    - The breadth of "comprehensible range" may vary by individual
        - It may also vary by task
- C: Further acceleration exceeds the comprehensible range, leaving humans puzzled
    - It's fundamentally wrong for humans and AI to synchronize their pace
- D: AI should leverage its speed to explore beyond human observation
    - AI can suggest, "After examining proposals 1, 2, and 3, proposal 3 seems promising, so let's proceed this way."
    - Humans can, of course, say no
    - They can also request exploration of more such proposals

## Background
<img src='https://scrapbox.io/api/pages/nishio/nishio/icon' alt='nishio.icon' height="19.5"/>
![image](https://gyazo.com/82fb8fc67dfd45134df0b0ba495e1edf/thumb/1000)
- The acceleration of [[idea generation]] by AI leads to issues when it goes beyond the [[range of human comprehension]], causing uncertainty in how to revert changes
    - Is it incorrect to regulate faster entities at our slower pace?
    - How can a slow entity like myself avoid becoming a bottleneck?

<img src='https://scrapbox.io/api/pages/nishio/GPT5/icon' alt='GPT5.icon' height="19.5"/>
The issues of "regulating fast entities with a slow self" and "being unable to revert when comprehension is lost" are easier to manage separately.
1. Divide roles: Don't aim to "understand everything"
    - ❌ Humans comprehensively track every event
    - ✅ Humans control "objectives and constraints" and "evaluation," while AI moves swiftly towards them
2. Mandate "compression for humans" in fast processes
    - Create a layered structure
        - L0: Raw trace (for AI)
        - L1: Short summaries of each step
        - L2: "Progress report" readable by humans in 1 minute
        - L3: "Summary of background and implications" readable by humans in 10 minutes
    - You usually only view L2 or L3.
    - However, if you can delve into L1/L0 for areas of interest, you can expand only necessary parts without following everything, reducing the risk of breakdown despite speed differences.
3. Address the "irreversible" issue with version control
    - The inability to revert stems from ambiguity about what constitutes "a single change."
4. Let fast entities audit each other (AI audits AI)
5. Focus human work on "direction-setting" and "meaning-making"
    - AI: Mass generation, exploration, trial and error
    - Humans:
        - Determining what is considered a problem (problem setting)
        - Designing which metrics to prioritize (evaluation criteria)
        - Assigning meaning to proposals, storytelling, and societal connection
    - Beyond selecting proposals, only humans can determine "why this proposal" and "what it means personally," so intentionally reserve this as human work.

---
This page is a high-quality translation from [/nishio/遅い自分はボトルネックだけど、それでも全体としては速く賢く動けている](https://scrapbox.io/nishio/遅い自分はボトルネックだけど、それでも全体としては速く賢く動けている). The original content is maintained by NISHIO Hirokazu.