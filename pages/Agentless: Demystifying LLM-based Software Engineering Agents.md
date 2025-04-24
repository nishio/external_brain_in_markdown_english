---
title: "Agentless: Demystifying LLM-based Software Engineering Agents"
---

[https://arxiv.org/abs/2407.01489](https://arxiv.org/abs/2407.01489)
<img src='https://scrapbox.io/api/pages/nishio-en/o1 Pro/icon' alt='o1 Pro.icon' height="19.5"/>
In this study, we propose [[AGENTLESS]] as a simple solution to the problems that arise from delegating complex tool operations and planning to LLMs (such as complicated tool design, unintended and wasteful processing, and lack of self-evaluation), while the [[autonomous agent]] ([[agent-based]]) approach of large-scale language models (LLMs) is increasingly used to automate software development tasks. AGENTLESS] is proposed as a simple solution to these problems.

AGENTLESS eliminates complex mechanisms that allow LLM agents to make autonomous decisions about which tools to use and when, how to plan their actions, and so on,
- Fault localization
- Generation of repair candidates (repair)
- Patch validation
The framework is simple, with a clear three-step process: "What files need to be fixed? The LLM is not asked to manipulate tools or the external environment, but only to filter the candidate patches. The LLM does not manipulate tools or the external environment, but only plays the role of filtering candidate patches.

In the evaluation with SWE-bench Lite (a benchmark containing actual issues on GitHub and corresponding Python code),
- AGENTLESS correctly resolved **32.00%** of issues and outperformed existing open source agent methods.
- The inference cost per case is also kept low at $0.70.

In addition, the paper results from a detailed classification of SWE-bench Lite issues,
- The issue description itself may be inadequate or misleading,
- The patch itself, which is the solution, may be included in the issue text,
The report points out that there are issues such as the following. A new, more rigorous benchmark, SWE-bench Lite-S, was constructed to exclude these problematic issues, and AGENTLESS was shown to be equally effective here. OpenAI has also created its own filtering data set (SWE-bench Verified) based on AGENTLESS.

In general, this study suggests that a step-by-step and simple method (AGENTLESS), which does not necessarily rely on complex agentic methods for LLM utilization in software development tasks, can be both highly effective and low-cost, and is expected to provide a new baseline or starting point for conventional agent approaches. It is expected to provide a new baseline or starting point for conventional agent approaches.

---
This page is auto-translated from [/nishio/Agentless: Demystifying LLM-based Software Engineering Agents](https://scrapbox.io/nishio/Agentless: Demystifying LLM-based Software Engineering Agents) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.