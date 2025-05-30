---
title: "Toolformar"
---

<img src='https://scrapbox.io/api/pages/nishio-en/GPT-4/icon' alt='GPT-4.icon' height="19.5"/> Briefly describe Toolformer in bullet points.
- Toolformer is a model that [* allows language models to use external tools (search engines, calculators, calendars, etc.).
- Because existing approaches often require large amounts of human annotation or are limited to task-specific settings, Toolformer proposes a different approach.
- Use large language models and in-context learning to generate API use cases and train the models to learn API calls.
- Use a self-supervised loss function to determine which API calls are useful for token prediction.
- Fine-tune the language model with API calls deemed useful.
- Toolformer achieves excellent results on a variety of tasks with zero shots after learning to use the tool.
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>In other words, ### teach AI how to use external tools such as groupware
 (This is a story in the Cybozu context: from [[a study group about connecting my Scrapbox to ChatGPT]])
- Manipulate external tools as needed to pull information, read it, and make decisions.
- Information about what kind of operation you want is embedded in the response text in microformat.
- ![image](https://gyazo.com/d2fad242e843c88d9718a872aae62a90/thumb/1000)

abstract
> Language models (LMs) demonstrate a remarkable ability to solve new tasks from a few examples or textual instructions, especially on a large scale. They can also, paradoxically, struggle with basic functions that simpler, smaller models excel at, such as arithmetic and fact retrieval. In this paper, we show that LM can learn how to use external tools via a simple API and achieve the best of both worlds. We present Toolformer, a model that is trained to determine which API to call, when to call it, what arguments to pass, and how best to incorporate the results into future token predictions. This will be done in a self-supervised fashion, requiring only a handful of demonstrations for each API. Incorporating a variety of tools, including a calculator, a Q&A system, two different search engines, a translation system, and a calendar, Toolformer significantly improves zero-shot performance on a variety of downstream tasks without sacrificing its core language modeling capabilities, often far able to compete with larger models.
[https://arxiv.org/abs/2302.04761](https://arxiv.org/abs/2302.04761)


[https://zenn.dev/qwegat/articles/4fb99ad25f3f36](https://zenn.dev/qwegat/articles/4fb99ad25f3f36) on an approach to make ChatGPT remember Ctrl+F.
- > [nishio](https://twitter.com/nishio/status/1638018805430640640) I feel this is the germ of a genius idea. I mean, if ChatGPT can express in words the "search behavior" it wants to do, it can be coupled with a system that receives it and does the search behavior for it that ChatGPT cannot do (whether that system is human or search is trivial).
    - > [yuniruyuni](https://twitter.com/yuniruyuni/status/1638334809603993603) Nice to meet you! There is a Toolformer [https://arxiv.org/abs/2302.04761](https://arxiv.org/abs/2302.04761) that has exactly this idea of "using other systems" at the point of learning, and it seems to result in a significant improvement in zero-shot performance...!
    - > [nishio](https://twitter.com/nishio/status/1638347965625667584) Thanks for the info! I will read it!
- > [yuniruyuni](https://twitter.com/yuniruyuni/status/1638333706044837889) This is equivalent to the Toolformer( [https://arxiv.org/abs/2302.04761](https://arxiv.org/abs/2302.04761) ) introduced the other week. It's like a prompt engineering implementation of the same idea as Toolformer(  ) introduced the other week...!
- > [yuniruyuni](https://twitter.com/yuniruyuni/status/1638335295258234880) LLM can, even at this point, verbalize what to do for a queried objective. So if there is a coupling with an external system, it should be possible, if done well, to run a feedback loop that goes looking for outside events on its own. And if you have this built in at the point of learning, like Toolformer...?
