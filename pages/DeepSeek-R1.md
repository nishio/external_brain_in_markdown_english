---
title: "DeepSeek-R1"
---

[deepseek-ai/DeepSeek-R1](https://github.com/deepseek-ai/DeepSeek-R1?tab=readme-ov-file)
[Paper (PDF)](https://github.com/deepseek-ai/DeepSeek-R1/blob/main/DeepSeek_R1.pdf)Abstract
<img src='https://scrapbox.io/api/pages/nishio-en/o1 Pro/icon' alt='o1 Pro.icon' height="19.5"/>
DeepSeek-R1 is a series built around large-scale reinforcement learning (RL) to enhance the inference power of large-scale language models (LLMs). First, we developed DeepSeek-R1-Zero, in which RL was applied directly to the base model without supervised data, and showed that it could acquire advanced inference capabilities. However, problems with readability and language mixing remained, so we proposed DeepSeek-R1 by introducing a small amount of "long thought-processed" teacher data (cold-start data) of several thousand cases, combined with a stepwise training pipeline. Finally, we achieved the same level of inference performance as OpenAI's o1-1217.

We have also investigated distillation of the trained DeepSeek-R1 into lightweight models such as Qwen and Llama as "teacher models," and have shown that high inference performance can be achieved even with small models. In particular, small models such as Qwen-7B, 14B, and 32B have significantly improved performance, achieving results comparable to OpenAI's small models. In general, the study paves the way for the development of small, high-performance inference-specific LLMs by combining RL and distillation.

Expert opinion
> [hillbig](https://x.com/hillbig/status/1881471978252705822) DeepSeek-R1 achieves significant improvement in inference performance through reinforcement learning. It achieved an o1-like long-term inference process with only the rewards of reinforcement learning. This is believed to be the first example where the learning details of a model comparable to o1 are described.
>
>  First, we evaluated how much capability could be acquired from the base model by reinforcement learning alone (DeepSeek-R1-Zero).
>  [[GRPO]] is used as reinforcement learning. It does not use the value function or the Critic, Reward model, but optimizes measures based on the reward score of each group.
>  G outputs were sampled for each question. Improved log-likelihood ratio of the post-opening measure to the original measure after each reward was subtracted from the mean of all rewards and normalized by the standard deviation to be Advantage.
>  (probably any RL method itself)
>
>  We used rule-based rewards. In the case of math, the reward was the answer, and in the case of programs, the reward was the compiler result or whether the test case was passed. We also used whether the format was followed. In the later discussion, it is noted that we tried other rewards ([[Process Reward Model]], [[MCTS]]), but they did not work because the model hacked the rewards or fell into local solutions.
>
>  During this reinforcement learning process, performance improved by thousands of steps, and "Aha" moments were found where the model found new solution strategies through its own trial-and-error. As it learned, it also gained the ability to think longer to solve complex problems.
>
>  On the other hand, the resulting model had problems with readability and mixing of multiple languages.
>
>  Because of these problems, R1
>  SFT -> Large RL for inference tasks -> SFT for tasks -> RL for all tasks
>  The study was conducted in four processes.
>  First SFT used small amounts of high quality data to improve readability; subsequent large scale RL added language consistency rewards
>
>  distillation to dense models used these models as teacher data. It has been reported that performance was much better when distilled than when small models were directly RLed to large scale
>
>  ==
>  The above results suggest that only a somewhat strong model may be able to improve its own performance in large-scale reinforcement learning.
>  External rewards are also important, and in this case it was mathematics, code, and formats that were rewarded on a rule basis. External rewards would be easy to design for software engineering and agents as well, which will be important now

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
In some strong models, reinforcement learning can make them stronger
- This would refute the "we've used up all the data on the Internet, so we can't be smart anymore" kind of rumor.
- For tasks such as mathematics and programming, where the cost of determining whether the correct answer is correct or not is low, reinforcement learning using this as a reward function will help you acquire a "knack for thinking" and jump-start the rate of correct answers.
- Also, the "smart large-scale model" created here became the teacher, and by learning the smaller models, the smaller models also became smarter.
    - ![image](https://gyazo.com/b64092d8b5a2ff91f11fdb5b884de35b/thumb/1000)
    - 14B~32B over o1-mini
    - Given that 4o is sufficient for the majority of daily human tasks, 1.5B may be sufficient for some content
        - →The possibilities for LLM's own hosts have greatly expanded.

> This code repository and the model weights are licensed under the MIT License.

Talk about the thought process being in Chinese when the instructions are in Japanese.
- Maybe it happens sometimes, but as far as I've tried, it's been in English.

[https://ollama.com/library/deepseek-r1:32b/blobs/6150cb382311](https://ollama.com/library/deepseek-r1:32b/blobs/6150cb382311)

Run deepseek-r1:32b with ollama
- [https://gist.github.com/nishio/85f621c5944971652228cdab417bb113](https://gist.github.com/nishio/85f621c5944971652228cdab417bb113)
- It's like a mere MacBook in your hand that works so well!

Talk about a weak ethical filter compared to o1.
- Don't think so.
    - [https://gist.github.com/nishio/222dfb4ddeef551b9e993a49707c4f4c](https://gist.github.com/nishio/222dfb4ddeef551b9e993a49707c4f4c)

---
This page is auto-translated from [/nishio/DeepSeek-R1](https://scrapbox.io/nishio/DeepSeek-R1) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.