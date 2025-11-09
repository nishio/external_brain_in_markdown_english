---
title: "Codex"
---


<img src='https://scrapbox.io/api/pages/nishio-en/GPT5/icon' alt='GPT5.icon' height="19.5"/>
Codex (2025 Edition) Overview
- What it is: OpenAI's suite of agents for software engineering. Works both locally (CLI/IDE) and in the cloud, included in ChatGPT paid plans (Plus/Pro/Team/Edu/Enterprise); CLI can be installed with `npm i -g @openai/codex`. Recommended model is GPT-5. ([OpenAI](https://openai.com/codex/?utm_source=chatgpt.com)) ([OpenAI [https://openai.com/index/introducing-gpt-5-for-](https://openai.com/index/introducing-gpt-5-for-) developers/?utm_source=chatgpt.com])
- What can be done (typical examples): feature additions, bug fixes, code base Q&A, test execution, PR suggestions. Each task can be executed in parallel in a cloud sandbox loaded with a repository. ([OpenAI](https://openai.com/index/introducing-codex/?utm_source=chatgpt.com))
- Where it works and integration: Terminal/IDE/Web/GitHub/iOS with same account, VS Code-like IDE extension, ChatGPT sign-in (no API key required), local↔cloud state transfer, support for PR auto-review and @codex mentions. ([OpenAI Help Center](https://help.openai.com/en/articles/6825453-chatgpt-release-notes?utm_source=chatgpt.com))
- Model: Codex is the name of the agent product, and the latest model is responsible for internal code generation and inference; GPT-5 has been publicly announced as superior to o3 in practical coding (SWE-bench and other practical evaluations/examples). ([OpenAI](https://openai.com/index/introducing-gpt-5-for-developers/?utm_source=chatgpt.com))
- Data/Privacy: Input and output for business use such as ChatGPT Team/Enterprise/API are not used for training by default (can be opted in by the organization). ([OpenAI Help Center [https://help.openai.com/en/articles/10306912-sharing-feedback-evaluation-and-fine-tuning-data-and-api-inputs-and](https://help.openai.com/en/articles/10306912-sharing-feedback-evaluation-and-fine-tuning-data-and-api-inputs-and) -outputs-with-openai?utm_source=chatgpt.com])

History and Positioning
- 2021: Launch of the "OpenAI Codex" (a family of codes additionally trained on GPT-3), a natural language to code product. Later the API is terminated and the current Codex product line is redesigned as "agents" in 2025. ([OpenAI](https://openai.com/news/product/?limit=18&sortBy=old&utm_source=chatgpt.com))

How to start (shortest)
1. `npm i -g @openai/codex`
2. sign in to ChatGPT with CLI/IDE extension
3. connect the repository and throw tasks (e.g. `codex fix tests`, `codex propose pr
(See official Codex developer site and release notes for detailed guide) ([OpenAI](https://openai.com/codex/?utm_source=chatgpt.com), [OpenAI Help Center [https://help.openai.com](https://help.openai.com) /en/articles/6825453-chatgpt-release-notes?utm_source=chatgpt.com])

---
> [ringo](https://x.com/ringo/status/1961071380243574796) When I started using codex, I thought it was inconvenient that I couldn't see the diffs.
>  After a few days of use, I found I didn't need it.
>  I also found it inconvenient that the result of the command execution is truncated, but I'm finding that I don't need that either.
> [ringo](https://x.com/ringo/status/1961072095598633163) I should leave the details to the agents and concentrate on seeing how they moved and figuring out what moves are right.
>  codex is designed that way.
>  I think the code became [[a detail]].
>  Is it close to being treated like bytecode or assembly?

Continued need to be able to visualize [what kind of product you want to make
- Related: [[I don't have anything I want to make...]]

---
This page is auto-translated from [/nishio/Codex](https://scrapbox.io/nishio/Codex) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.