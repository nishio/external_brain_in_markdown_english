---
title: "Adapting Large Language Models to Domains via Reading Comprehension"
---

Adapting Large Language Models to Domains via Reading Comprehension
[https://arxiv.org/abs/2309.09530](https://arxiv.org/abs/2309.09530)

![image](https://gyazo.com/d8182e07b5d193f08b8a9d5854400327/thumb/1000)


<img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/>This paper proposes a new method for adapting large-scale language models (LLMs) to domain-specific tasks. Main contents include:.
1. we found that simply continuing to pre-learn on a domain-specific corpus would result in the acquisition of domain knowledge but reduced prompting ability.
2. we propose a method to convert the raw corpus into "reading texts". Add tasks associated with each text, and also mix in some general instructions.
3. validated this methodology in three domains: biomedical, financial, and legal, and found consistent performance gains.
4. 7B-parameter models achieved performance comparable to 50B-parameter specialty models.
5. we have shown that domain-specific reading text improves performance in general benchmarks.
6. the method is computationally efficient and can be applied to a variety of pre-trained corpora.
7. code and data are publicly available.
    - [[LMOps]]

In short, the study proposed an efficient method for both acquiring domain knowledge and maintaining prompting ability, and demonstrated its effectiveness.


Reading text is the core of the methodology proposed in this paper. Specifically, it has the following characteristics

1. conversion process:
        - Converts the original domain-specific raw text into a format that includes a series of related tasks.

2. composition:
        - - original raw text
        - - Followed by several tasks related to the content of the text

3. the type of task:
        - - summary
        - - Text to word conversion
        - - natural language inference
        - - common sense reasoning
        - - paraphrase detection
        - - text completion
        - (lessening the significance or value of the previous word) the likes of

4. question and answer format:
        - These tasks are designed in a question-and-answer format.

5. purpose:
        - - Allow models to learn domain knowledge from raw text
        - - At the same time, improve their ability to respond to prompts through a variety of tasks

6. imitation of the human learning process:
        - It is inspired by the human learning process, in which learning is enhanced by solving practice problems after reading.

7. mixing with general instructions:
        - In addition, general instructions are mixed in to help them learn a variety of input/output patterns.

This approach allows the model to acquire domain-specific knowledge while also maintaining and improving its ability to respond to prompts. This is an effect that cannot be achieved by simply continuing to pre-learn on a domain-specific corpus.

---
This page is auto-translated from [/nishio/Adapting Large Language Models to Domains via Reading Comprehension](https://scrapbox.io/nishio/Adapting Large Language Models to Domains via Reading Comprehension) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.