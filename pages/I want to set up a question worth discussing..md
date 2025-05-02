---
title: "I want to set up a question worth discussing."
---


- [[IIDOBATA system]]
- Digital Democracy 2030 [Slack](https://w1740803485-clv347541.slack.com/archives/C08FF5MM59C/p1746014092924689)

Shutaro Aoyama (Burumo)
- On question generation:
    - When there are a large number of "issues" and "solutions" related to a certain topic, we want to set "questions" to be discussed from them.
    - I want to set up a question worth discussing.
    - Maybe there are two possible patterns of questions
        - The current situation is A. How can we make it B? (how question)
            - The current implementation is this way.
        2. the current situation is A, but should it be B? (GOAL question)
            - This looks like it should be there too.

NISHIO Hirokazu
- I'm still fuzzy on the question worth discussing, so I'll start by stirring it up more before I talk about how:.
- The fact that you say "two patterns" makes me feel like you're in a hurry to narrow it down too much.
    - The status quo is A."
    - The status quo is A. This is not good."
    - "The status quo is A, this is not good, what can we do to get out of it?"
    - Being a B is better than the status quo."
    - What do I have to do to get a "B?"
- I think there are 0 phases where B is not verbalized, 1 phase where there is one, and multiple phases.
- My intuition is that we should have a discussion on about three of them before narrowing it down to one.

relevance
    - [[Quantity of choices and quality of decision making]]
    - > Judgments are rated in three categories: "very good", "satisfactory", and "poor". (a,b,c below)
    - >  (a + b) / c was 7.7 times higher and a / (b + c) was 16.7 times higher when there were three choices than when there were two choices.

<img src='https://scrapbox.io/api/pages/nishio-en/o3/icon' alt='o3.icon' height="19.5"/>
## 4 criteria to evaluate the question
.
Criteria/meaning & checkpoints/quantification tips
- Impact
    - Can you clearly state who stands to gain or lose and by how much?
    - Can you explain interests that involve "numbers" such as budgets, legal changes, cost of living, etc.?
    - Relationship Population x Estimated Change ≈ Coarse Expectations
- Divergence [[divergence]].
    - Range of values/conflicts of interest.
    - Score high if opinion is bimodal or higher.
    - "Pro/con ratio of 3:7 to 7:3" has the highest discussion value.
    - embedding Average of inter-cluster cosine distances
- Feasibility [[feasibility]].
    - Room for conclusions to fall into action.
    - "Can the authority try it in one step?"
    - The closer to the existing system and technology, the higher.
    - Number of resources required for minimum implementation / duration
- Timeliness
    - Deadline/window availability.
    - Are there "time pressures" such as budget requests, bylaw changes, before and after events, etc.?
    - Inverse of number of days remaining (the closer the closer, the higher)

Tip: If Impact and Divergence are high, and Feasibility and Timeliness are "moderate or better", then it is the best for discussion.

impressions<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
- Which to choose when there are multiple potential questions
- Too low feasibility and timeliness are subject to foot-dragging.
    - What is digital democracy in 2030?" is too far away from the deadline, isn't it?
        - So it was a good move for the "Digital Democracy 2030" project to cut the time scope by saying, "We'll make and release useful tools before the July 2025 elections.
    - Good to see that viability also took the form of "create an OSS tool and release it to the public".
        - If it's "let the government do the Taiwan JOIN thing," it's no longer something that the project members can implement.
- The greater the impact, the better.
    - Feasibility and trade-offs
- With Digital Democracy 2030's Slack, you have a group of people who have no objection to doing this kind of thing, so it's less divergent.
    - It would be interesting to discuss this with a 50-50 group of people outside the project who are unfamiliar with AI, vaguely afraid of it, or see it as an enemy.
    - There is an inherent difficulty in inviting AI haters into the AI discussion w
        - It would be nice if AI could emulate such a person.
        - When you start doing this, it becomes "why do people need to argue in the first place?

<img src='https://scrapbox.io/api/pages/nishio-en/o3/icon' alt='o3.icon' height="19.5"/>
Granularity of questions using frames (A→B→How)
- Current status (A: Descriptive)
    - Example: "The vacancy rate in Nakano Ward is 9%."
    - Discussion objectives: Fact checking and data sharing
    - Suitable criteria: Impact (scale in numbers)
- Evaluation (A Good/Bad: Evaluative)
    - Example: "A 9% vacancy rate undermines urban vitality."
    - Discussion Objective: To reach a consensus on "why it matters".
    - Suitable criteria: Divergence
- Goal Setting (B: Normative/Goal)
    - Example: "Less than 5% is desirable."
    - Purpose of Discussion: Clarification of "what it should be
    - Suitable criteria: Impact + Divergence
- Pathways of Change (How: Strategic)
    - Example: "How would you implement data linkage for properties with unknown owners?"
    - Discussion objective: divergence and refinement of policy ideas
    - Suitable criteria: Feasibility + Timeliness

impressions<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
- I feel like you're forcing the framework rather than the other way around.
- I don't think the use case we're envisioning would allow people to frame the discussion in a particular flow.

How to match grain size
- Situation/Recommended Granularity/Typical Failure
- Insufficient data, chaotic issues
    - (1) Current Status
    - Jump to How out of the blue
        - Don't you think that's too common?<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
            - "I think it would be good to do this!" There are too many people who suddenly say
            - So is software development.
            - We need to dig into "Why do you think we should do it?"
            - This is more of a question to the individual than a question to the whole place.
- Value conflicts become apparent
    - (2) Evaluation
    - "Everyone assumes it's a problem."
    - <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
        - As a result of digging into (1), it becomes clear that there are discrepancies in the values of "what is good and what is bad".
        - It's not good to have nuclear power plants operating, so they should be decommissioned immediately."
            - The implicit assumption in his mind is that "it is not good to have nuclear power plants operating," but in fact, this assumption varies from person to person.
            - High electricity bills are not good for the family budget, so nuclear power plants should be restarted."
- Goals are vague
    - (iii) Goal setting
    - List measures but cannot determine priorities
- implementation phase
    - (4) Change path
    - No decision makers, no deadlines, discussions spinning out of control
- <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
    - When considering the domain of policy discussion, there seems to be a point of contention as to whether the public should be involved up to (3) and (4), or whether they should do up to the visualization of the distribution of values in (2) and leave (3) and (4) to the politicians to choose between them.

---
This page is auto-translated from [/nishio/議論する価値のある問いを設定したい](https://scrapbox.io/nishio/議論する価値のある問いを設定したい) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.