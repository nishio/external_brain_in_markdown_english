---
title: "Ollama"
---

2024-04-26
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>What is OLLAMA? Search in English and explain in Japanese.

<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>Ollama is an open source application designed to make it easy to run, create, and share large language models (LLMs) locally. The platform is available primarily for MacOS and Linux and operates through a command line interface. Initially supporting [[Llama2]] models, it has since expanded to support [[Mistral]] and [[Phi-2]] models as well.
- (Isaac Chung)[What is Ollama? A shallow dive into running LLMs locally | Isaac Chung](https://isaac-chung.github.io/blog/what-is-ollama)​

Ollama is unique in its ability to efficiently run large models without a GPU. This is achieved by quantizing the weights of the model and running some layers on the CPU and others on the GPU to achieve efficient inference. This allows even large models to run within limited local resources.
- (Mitja Martini)[Ollama on Windows: How to Install and Use it with OpenWebUI | Mitja Martini](https://mitjamartini.com/posts/ollama-on-windows/)

The main reason for using Ollama is the ability to run large language models securely on your own hardware without relying on third-party cloud servers. This allows you to customize and extend your own models as needed while protecting the privacy of user data. It also makes it easy to download, manage, and run models, and to experiment with different models.
- (GitHub) [ollama/ollama: Get up and running with Llama 3, Mistral, Gemma, and other large language models.](https://github.com/ollama/ollama)
- (Isaac Chung)

In general, Ollama is suitable for users with programming skills and those who want to run language models in their own environment without using third-party services.


> [_saip_](https://twitter.com/_saip_/status/1783309599480668508) Ollama, install.
>  $ ollama run phi3
>  I can use [[Phi-3]] immediately, the experience is amazing!
>  The first time you have to pull it, but after the second time you can use it quickly and there is no model loading or anything...? I'm not sure.
> [_saip_](https://twitter.com/_saip_/status/1783310216827990465) On a local environment with 8GB of VRAM, it was generating Japanese so fast that I had to pull it out. The text was incoherent, but it seemed to be Instruction Tuning, so I thought that if I wrote instructions properly, it would work well. I thought it would work well if I wrote the instruction properly.

---
This page is auto-translated from [/nishio/Ollama](https://scrapbox.io/nishio/Ollama) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.