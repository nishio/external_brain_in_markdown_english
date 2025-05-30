---
title: "BERT"
---

BERT: Pre-training of Deep Bidirectional [[Transformer]]s for Language Understanding
[https://arxiv.org/abs/1810.04805](https://arxiv.org/abs/1810.04805)

Explanatory slides [[BERT and Transformer]].

[https://github.com/google-research/bert](https://github.com/google-research/bert)

In 2017, it was shown that [[Transformer]] without [[RNN]] and without [[CNN]], consisting only of [[attention mechanism]], performs well in translation tasks
> We propose a new simple network architecture, the Transformer, based solely on attention mechanisms, dispensing with recurrence and convolutions entirely.
[[BERT]] is an extension of that trend.

- Created a model that allows pre-training.
- Simply by adding an output layer to the pre-trained model, we were able to achieve good results in 12 different language comprehension tasks.
- Transformer

The same trend that has made it easy to use pre-trained models for image recognition tasks for field applications is likely to occur in natural language processing in the future. (But what about minor languages such as Japanese...)(Ha, would you rather the government professionals create a nice pre-trained model and distribute it for free?) (By all means, with the intention of getting it done in time before the Olympics)

> BERT: Bidirectional Encoder Representations from Transformers.

> proposing a new pre-training objective: the “masked language model” (MLM), inspired by the Cloze task (Taylor, 1953).
- Cloze task is so-called "fill-in-the-blanks" problem

> we also introduce a “next sentence prediction” task that jointly pre-trains text-pair representations.

The Transformer implementation uses the original `tensor2tensor` library, and nothing was tampered with.

[The Annotated Transformer](http://nlp.seas.harvard.edu/2018/04/03/attention.html)

The word is split in WordPiece as `he likes play ##ing`, with embedded position and sentence number information
Task to mask 15% at random and predict what is masked.
- Not all of them are MASK tokens.
- MASK 80% of 15%, 10% random words, and 10% words as they were
- <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>So even seemingly ordinary words may be questioned later.


- [[Curriculum Learning]] equivalent may be happening.
    - Learning [[MaskLM]] is easier than other tasks

[https://twitter.com/_Ryobot/status/1050925881894400000](https://twitter.com/_Ryobot/status/1050925881894400000)

[Running BERT, a general-purpose language expression model, in Japanese (PyTorch) - Qiita](https://qiita.com/Kosuke-Szk/items/4b74b5cce84f423b7125)

---
This page is auto-translated from [/nishio/BERT](https://scrapbox.io/nishio/BERT) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.