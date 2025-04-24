---
title: "Agentic RAG"
---

<img src='https://scrapbox.io/api/pages/nishio-en/DR/icon' alt='DR.icon' height="19.5"/>
## Agentic RAG (Retrieval-Augmented Generation) Definition and Characteristics
.
- Agentic RAG incorporates an autonomous AI agent within the framework of traditional RAG (text generation combined with external knowledge retrieval). While regular RAGs perform information retrieval and generation in a series of static steps, Agentic RAGs are designed so that the agent behaves actively, performing multi-step reasoning and dynamic information gathering.
    - [Agentic Retrieval-Augmented Generation: A Survey on Agentic RAG](https://arxiv.org/abs/2501.09136)

The main characteristics are as follows
- Autonomous Agent Integration: incorporates an agent (LLM-based) into the information retrieval pipeline to independently plan and execute the best search strategy for a user's query.
- [[Advanced Design Patterns]]: Agents utilize reflection, planning, tool use, and multi-agent collaboration to improve search queries and search for new sources of information as needed. We repeatedly search for new sources of information and improve search queries as needed.
- Increased flexibility and adaptability: Because it is not tied to a static workflow, it can adapt to complex tasks and incremental reasoning. This dramatically improves flexibility, scalability, and situational awareness, making it applicable to a wider range of applications (medical, financial, educational, etc.).
- Up-to-date: Because data can be retrieved and integrated in real time from the Internet and other sources, models that rely on static training data can generate more up-to-date and contextualized responses than models that rely on static training data.

These Agentic RAG concepts are also related to trends such as the "[[ReAct]]" approach, which combines multi-step reasoning and tool use, and is positioned as a next-generation framework to make generative AI more autonomous and powerful.

[https://chatgpt.com/share/67a1b286-fe18-8011-ace6-3c432e38d15c](https://chatgpt.com/share/67a1b286-fe18-8011-ace6-3c432e38d15c)

## [[Agentic Retrieval-Augmented Generation: A Survey on Agentic RAG]]
<img src='https://scrapbox.io/api/pages/nishio-en/o3-mini-high/icon' alt='o3-mini-high.icon' height="19.5"/>
This paper provides a comprehensive description of the concept of "### Agentic RAG
", its development, implementation methods, and potential applications, integrating ### Agents (autonomous AI)
 to overcome the limitations of traditional [[Retrieval-Augmented Generation]] ([[RAG]]) systems. The following is a brief summary of the main points. Below is a brief summary of the main points.

1.### Background and Issues
.
    - Traditional RAGs compensate for the limitations of static knowledge (outdated information and lack of context) by combining the generative power of LLMs (large-scale language models) with external information retrieval.
        - However, simple keyword searches and one-way workflows make complex multi-step inferences and dynamic situational responses difficult, and there are challenges with contextual integration and response accuracy.

2.### Agentic RAG features
.
    - autonomous decision making and iterative processing.
        - Agents dynamically optimize workflows by evaluating search results (reflection), decomposing tasks (planning), leveraging external tools, and collaborating among multiple agents.
    - Flexible workflow design.
        - Multiple patterns are proposed to match the nature of the task, including prompt chaining, routing, parallel processing, orchestrator-worker, and evaluation-optimization.

3.### Evolutionary process and classification of RAGs
.
    - Naïve RAG → Advanced RAG → Modular RAG → Graph RAG → Agentic RAG
    - It has evolved from simple keyword-based methods in the early days to methods using semantic search (Dense Retrieval) and graph structure, and finally to dynamic adaptive capabilities by incorporating agents.
    - A variety of architectures are classified and studied according to purpose and application domain, including single-agent, multi-agent, hierarchical, compensating, adaptive, and even graph-integrated architectures.

4.### Applications and implementation support tools
.
    - Application Area:
        - It can be applied to a wide variety of real-world scenarios, including customer support, medical diagnostics, legal and contract analysis, financial risk assessment, education, and even multimodal (including image and video) information processing.
    - Tools/Frameworks:
        - Various libraries that support the construction of agent-integrated systems while leveraging existing ecosystems, such as LangChain, LlamaIndex, Hugging Face, CrewAI, OpenAI Swarm, Vertex AI, and Semantic Kernel, are introduced. The following libraries will be introduced.

5.### Evaluation criteria and future issues
.
    - BEIR, MS MARCO, and HotpotQA are presented as benchmarks, and issues for practical application are also identified, such as coordination among agents, efficiency of computing resources, and consideration of ethical aspects.

### Summary
.
Agentic RAG is a new paradigm that overcomes the limitations of conventional static and linear RAG systems with autonomous decision-making by agents and multi-stage reasoning to achieve more flexible and contextual information generation. This greatly improves real-time performance and the ability to respond to complex tasks, and is expected to be used in groupware and other fields that aim to improve intellectual productivity.


---
This page is auto-translated from [/nishio/Agentic RAG](https://scrapbox.io/nishio/Agentic RAG) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.