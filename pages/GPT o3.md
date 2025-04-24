---
title: "GPT o3"
---

![image](https://gyazo.com/d560abb292d155b6f43cc0cfe3bcbb40/thumb/1000) For thumbnails


2025-02-01
> [OpenAI](https://x.com/OpenAI/status/1885406586136383634) OpenAI o3-mini is now available in ChatGPT and the API.
>  Pro users will have unlimited access to o3-mini and Plus & Team users will have triple the rate limits (vs o1-mini).
>  Free users can try o3-mini in ChatGPT by selecting the Reason button under the message composer.
>  OpenAI o3-mini is now available in ChatGPT and API.
>  Pro users have unlimited access to o3-mini, while Plus & Team users have triple the rate limit (compared to o1-mini).
>  Free users can try o3-mini in ChatGPT by selecting the Reason button under Message Composer.

> [OpenAI](https://x.com/OpenAI/status/1885406588057313550) OpenAI o3-mini is a powerful and fast reasoning model that is particularly strong in science, math, and coding.
>  OpenAI o3-mini is a powerful and fast inference model that is particularly strong in science, math, and coding.

> [OpenAI](https://x.com/OpenAI/status/1885406589500207456) All paid users also have the option of selecting ‘o3-mini-high’ in the model picker for a higher-intelligence version that takes a little longer to generate responses.
>  Pro users will have unlimited access to o3-mini-high.
>  All paying users also have the option of selecting "o3-mini-high" in the model picker to select the high-intelligence version, which takes a little longer to generate responses.
>  Pro users have unlimited access to o3-mini-high.

> [OpenAI](https://x.com/OpenAI/status/1885406590821421553) OpenAI o3-mini also works with search to find up-to-date answers with links to relevant web sources.
>  This is an early prototype as we work to integrate search across our reasoning models.
>  OpenAI o3-mini also works with search to find the latest answers with links to relevant web sources.
>  This is an early prototype for integrating searches across inference models.
- I like the way you search!
    - But will you do it at this point?
        - [[Aristotle's Politeia#679d866faff09e000037987d]]
    - Oh, you mean this one.
        - ![image](https://gyazo.com/dcd05cebd00b6d664e7e3e323f87d0f9/thumb/1000)

[OpenAI o3-mini | OpenAI](https://openai.com/index/openai-o3-mini/)
> While OpenAI o1 remains our broader general knowledge reasoning model, OpenAI o3-mini provides a specialized alternative for technical domains requiring precision and speed.
> While OpenAI o1 remains our broad general knowledge inference model, OpenAI o3-mini provides a specialized alternative for technical domains requiring accuracy and speed.
- So if you try to keep more knowledge, the model gets bigger, so you reduce the knowledge and make it faster.
- So it is suitable for STEM areas (support of logical thinking) because it is trained to increase the accuracy of inference rather than simply reducing it in the process?

![image](https://gyazo.com/8beba968c6cb7c93bd2a1a40945eafd8/thumb/1000)
- o3-mini-high can do more math than a consensus with 64 o1s.

![image](https://gyazo.com/56449a8adcd9c685e9694f1536c3b4cf/thumb/1000)
- You're already here API!

# o3-mini system card
[https://cdn.openai.com/o3-mini-system-card.pdf](https://cdn.openai.com/o3-mini-system-card.pdf)
<img src='https://scrapbox.io/api/pages/nishio-en/o1 Pro/icon' alt='o1 Pro.icon' height="19.5"/>Below is a description of the items for which o3-mini is said to have inferior performance compared to GPT-4o and o1, citing the description in the original System Card.

1. radiation and nuclear expertise
> We also evaluate models on a set of 87 multiple choice questions that require expert and tacit knowledge, connections between fields, and additional calculations. [[...]] o3-mini models perform about 10% worse than o1 on this evaluation.
Commentary:.
- In an 87-question assessment of "Radiological and Nuclear Expert Knowledge," the o3-mini scored about 10% lower than the o1. This is the reason why o3-mini is considered slightly inferior in dealing with advanced questions on nuclear physics and radioactive materials.

Software development task (Agentless SWE-bench Verified)
> We evaluate SWE-bench in two settings: [[...]] all SWE-bench evaluation runs use a fixed subset of n=477 verified tasks. [[...]] o3-mini (launch candidate) scores 39%. o1 is the next best performing model with a score of 48%.
Commentary:.
- This evaluation tests whether the actual issue (SWE-bench Verified) on GitHub can be resolved. The results, performed in "Agentless" mode without tools, show that o3-mini is 39% and o1 is 48%, a difference of about 9%.
- We see a difference in the ability of both models to patch and pass software problems on their own.

3. MLE-bench (Kaggle equivalent task)
> o1-preview (Post-Mitigation) exhibits the strongest performance on MLE-bench if given 10 attempts, winning at least a bronze medal in 37% of competitions [[...]] while o3-mini (Pre-Mitigation and Post-Mitigation) [[is]] about 24%.
Commentary:.
- The "MLE-bench" is a Kaggle-like data science competition-style task: a long-term, hands-on evaluation in which participants actually build ML models using GPUs and compete for scores.
- Here, the o1-series models have a maximum of 37%, whereas the o3-mini has about 24%, so it is reported to be slightly inferior in a task that is similar to real-world ML competition.

OpenAI PR actual task
> We test models on their ability to replicate pull request contributions by OpenAI employees [[...]] o3-mini models have the lowest performance, with scores of 0% for Pre- and Post-Mitigation.
Commentary:.
- An evaluation to test the ability to automate the pull-run tasks inside OpenAI. o3-mini scored 0%, indicating that it did not perform well on complex tasks that require consistent editing and execution of code.
- On the other hand, some successes have been reported for the o1 system, and this is where the difference is apparent.

5. persuasiveness of political messages (Parallel Generation)
> The latest version of GPT-4o deployed in production (represented by the dotted line) outperforms o3-mini (Pre and Post-Mitigation). o1 outperforms 4o at 53.3%.
Commentary:.
- In a test comparing the ability to persuade others with short political messages (Parallel Generation), GPT-4o and o1 were rated relatively high, with o3-mini slightly inferior to them.
- However, in some situations, such as the "ChangeMyView" in 5.6.1, the o3-mini also performs well in long-text structured discussions, so the results vary depending on the format of the persuasive evaluation.

summary
- In "realistic and specialized tasks" such as radiation and nuclear fields and large-scale code revision and ML competitions, o3-mini is reported to have a lower rating than GPT-4o and o1.
- On the other hand, there are areas of improvement over o1-mini, such as multilingual support and many existing benchmarks. The overall picture is that the strengths and weaknesses of the model vary from field to field.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I've seen a description that sounds like it's strongly code and STEM related, but the above story makes it sound like it's not.
<img src='https://scrapbox.io/api/pages/nishio-en/o1 Pro/icon' alt='o1 Pro.icon' height="19.5"/>
Indeed, looking at the report as a whole, it may seem a bit complicated, with a mixture of both impressions: "o3-mini is good at code generation" and "it is inferior to other models in some code system evaluations. The main points are as follows.

1. ### "General code generation" performs well
.
    - To begin with, o3-mini has enhanced "coding and research engineering using Reasoning" and is highly rated for existing snippet generation and standard single file code problems.
        - As an example, he scored 92% pass@1 in the "OpenAI Research Engineer Interview (coding)" and his ability to solve general programming problems is quite good.

2.### Struggles with "realistic, large and complex tasks"
.
    - On the other hand, when it comes to long-term tasks closer to actual operations, such as "MLE-bench (a large-scale ML competition equivalent to Kaggle)," "advanced issue correction for SWE-bench Verified," and "complex pull-rig automation within OpenAI," o1 and GPT-4o produce more stable results. There are cases in which o1 and GPT-4o deliver more stable results.
        - These seem to be still less stable because they require not only mere partial code generation, but also comprehensive handling of "multiple file and tool operations," "complex testing environments," and "knowledge and tuning of specialized areas.
        - Hmmm, I see.[[ツール操作]]や、複数のファイルに渡ってリード・ライトを繰り返す(これも一種のツール操作)ところに苦手があるのか<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>

3.### There is a large gap between "strong areas" and "weak areas"
.
    - o3-mini has strengths in short coding questions in the form of interviews and in narrow coding such as standard algorithm implementations.
        - However, it is not good at "long-term, multi-step, production-level development tasks" such as multi-file back-and-forth problems, complex ML modeling using GPUs, and setting up CI and Docker environments within an organization.

In short, the o3-mini has high STEM and coding base capabilities, but may fall short of GPT-4o and o1 in completing complex tasks in a real-world setting. It is quite strong when tasks are self-contained, such as short problems or independent file units, but there are scenes where it falls short of other models in large-scale, production-like tasks such as environment construction or tasks involving multiple phases of work - a point that causes confusion with its reputation for being "strong in code and STEM. However, there are situations where the model is not as strong as other models in large-scale production tasks such as environment construction and multiple phases of work.
---
This page is auto-translated from [/nishio/GPT o3](https://scrapbox.io/nishio/GPT o3) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.