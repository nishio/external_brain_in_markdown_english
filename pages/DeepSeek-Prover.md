---
title: "DeepSeek-Prover"
---

[https://arxiv.org/abs/2408.08152](https://arxiv.org/abs/2408.08152)
<img src='https://scrapbox.io/api/pages/nishio-en/GPT/icon' alt='GPT.icon' height="19.5"/>
DeepSeek-Prover-V1.5 is an open-source large-scale language model (LLM) developed for [[theorem proving]] on [[Lean 4]], evolving in the following ways

Innovation in Approach
- Fusion of whole proof generation and step proofs
    - Introducing the "truncate-and-resume mechanism" that integrates the advantages of the conventional "whole proof generation (batch generation of all proof codes)" and "step proof generation (verification of one step at a time)". The code is split at the error point and the next step is generated.
- Monte-Carlo Tree Search (MCTS)
    - A new algorithm, RMaxTS, was introduced to streamline proof search. Promotes diversity in solution paths by utilizing search at error locations and "curiosity rewards".

Learning Methods
- prior learning
    - Enhanced LLM with math and code data.
- Supervised fine-tuning
    - Extend the dataset to incorporate the tactic state of the proof into the model.
- Reinforcement Learning (RL)
    - [[Lean 4]] proof feedback is used as a reward to optimize the model.

Assessment Results
- [[miniF2F]] (high school level math problems): 63.5% achievement rate (above the previous best of 54.5%).
- [[ProofNet]] (college-level math problems): 25.3% achievement rate (above previous best of 18.1%).

Conclusion and Significance
- Combines efficiency and flexibility through a hybrid of whole and step generation.
- Improved mathematical reasoning skills and achieved state-of-the-art results.
- Further search strategies and applications to multi-theorem proving are expected in the future.
- This study demonstrates new possibilities for integrating proof support systems and LLMs.

---
This page is auto-translated from [/nishio/DeepSeek-Prover](https://scrapbox.io/nishio/DeepSeek-Prover) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.