---
title: "Fine-Tuning Llama-2: A Comprehensive Case Study for Tailoring Models to Unique Applications"
---

Fine tuning guide for [Llama2
- [Fine-Tuning Llama-2: A Comprehensive Case Study for Tailoring Models to Unique Applications](https://www.anyscale.com/blog/fine-tuning-llama-2-a-comprehensive-case-study-for-tailoring-models-to-unique-applications)

Fine tuning case studies by companies that provide fine tuning services using their own services
- We should think of it as, "Here's an example of what worked best out of the many we tried."

Llama-2 model
- Validated with three real-world use cases
- Fine tuning improves accuracy


Better than GPT-4 in some niche cases
- Functional Expression Extraction from Unstructured Text (ViGGO)
- SQL generation (SQL-create-context)
- 7B is sufficient for both.
    - On the other hand, as for the math comprehension task GSM, even 70B doesn't quite catch up.

- In particular, Llama-13b improved accuracy from 58% to 98% in function representation, from 42% to 89% in SQL generation, and from 28% to 47% in GSM.

Fine-tuning basics
In all three tasks, we use standard fine tuning techniques for all parameters.
- The model is fine-tuned to predict the next token
- All parameters in the model are subject to gradient update
- Block freezing and LoRA are not used.
- Ray makes it easy (advertisement).


Shard data between workers
Model sharding with DeepSpeed


special token
- Structuring tasks with special tokens instead of directing them with natural sentences
    - Does that learning improve performance for instructions in natural text? Does it ignore how to convert them otherwise?
    - Sounds like the latter, that if for some reason structured input can be obtained, it is better to use tokens that do not appear in natural text to clearly convey structure.


Explanation of ViGGO
- Okay, it looks like the problem is that we expect to interact according to fairly strict rules, and if we communicate those strict rules in natural sentences, even GPT4 can't do it well.

Effectiveness of Fine Tuning
> In an earlier blog post, we discussed the idea that fine tuning is not about facts, but about form.
- [Fine tuning is for form, not facts | Anyscale](https://www.anyscale.com/blog/fine-tuning-is-for-form-not-facts)

Some important questions
- Does the base model encounter the task concept in the learning process?
    - New concepts not encountered are unlikely to be acquired through small-scale fine tuning.
- Will Fewshots improve the situation?
    - If it improves, fine tuning is likely to improve it further.
    - > because far more examples can be incorporated into the weights of the neural network inside the model.


ViGGO revolves around pattern recognition and requires a basic grasp of language and basic concepts, but does not require complex logical reasoning.
- More importantly: all the "facts" needed for the output are already embedded in the input
- I see, that type of task is why ViGGO was able to exceed GPT4 with 7B fine tuning.<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>

evaluation
- GPT4 is not very good at "keep the attributes in order" and by putting that on the determination of whether it's successful or not, it's down from 90% to 50%.
- Fine tuning keeps order.



SQL generation with Llama-2 fine-tuning model

- Why is fine-tuning promising?
    - > The success of this task depends on the LLM's ability to learn the "structure" of SQL and translate natural language into this structure
    - I guess this also means that the "form of output" is another pattern that's important to follow the rules tightly.<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>

result
- 7B fine tuning outperformed GPT-4 and 70B-chat
    - Seems to me that being learned for chatting would return and not follow the format.<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>


Arithmetic Reasoning for Elementary School Students (GSM8k)
- > The fine-tuning task on this data set is different from the previous two. As opposed to simply learning the structure, we wanted to see how well LLM could improve our ability to reason about math problems.

- Cut out at GPT-3.5 because it is difficult to verify if the answer is correctly answered when the answer is given in natural sentences.
    - Fine tuning the output so that it can be immediately cut out with a regular expression has reduced the cost of API calls.


The chat version has higher performance in 7B and 13B to begin with.
- Maybe the training data contains mathematical interactions.
- The chat version of the 70B 8-shot baseline is losing all of its
- Fine tuning increases performance and lowers token costs.

They've decided that 8k data points isn't enough, so they've taken the approach of increasing it even more, and they're saying it's even better.
- You're doing a great job.<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
---
This page is auto-translated from [/nishio/Fine-Tuning Llama-2: A Comprehensive Case Study for Tailoring Models to Unique Applications](https://scrapbox.io/nishio/Fine-Tuning Llama-2: A Comprehensive Case Study for Tailoring Models to Unique Applications) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.