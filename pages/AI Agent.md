---
title: "AI Agent"
---

Google's White Paper (2024-09).
[Agents | Kaggle](https://www.kaggle.com/whitepaper-agents)
- [https://drive.google.com/file/d/1oEjiRCTbd54aSdB_eEe3UShxLBWK9xkt/view](https://drive.google.com/file/d/1oEjiRCTbd54aSdB_eEe3UShxLBWK9xkt/view)
<img src='https://scrapbox.io/api/pages/nishio-en/o1 Pro/icon' alt='o1 Pro.icon' height="19.5"/>
1. agent overview
    - What is an agent?
        - A mechanism that allows interaction with external tools and external data that cannot be obtained with a stand-alone large-scale language model (LLM).
        - The model will be able to autonomously take in information, plan (reasoning), and act (e.g., API calls) using tools and other resources to achieve the user's goals.
    - Difference between agents and models
        - Simple model: infers and answers the user's question only once, based on the knowledge in the training data. No standard access to external APIs or data.
        - Agents: access to external data and use of external tools to solve problems with multi-turn (multi-turn) context management and execution plans.
2. agent core configuration (cognitive architecture)
    - He explains that there are three major components to an agent.
        - Model (language model)
            - Language models (LLMs) at the core of inference; "how to use which tools" and "answers to user questions" using inference frameworks such as ReAct, Chain-of-Thought, and Tree-of-Thoughts.
        - Tools
            - It is responsible for access to external systems and API calls that cannot be made by the model alone.
            - For example, "Weather API", "Database Update API", "Google Flights API", "Google Search API", etc.
            - [[tool operation]]
        - [The orchestration layer
            - A mechanism that controls what is finally executed and in what order and how it is responded to, while receiving the output of the model and the results from the tool.
            - Here, the loop of "thinking → action → observation" is repeated many times to achieve the user's goal.
3. concrete reasoning and implementation flow
    - [[ReAct]], [[Chain of Thought]], [[Tree-of-Thoughts]]
        - Methods are introduced that allow agents to put their "thoughts" into writing (reasoning by explicitly indicating the thought process) and methods that further strengthen the intermediate steps leading to the solution.
        - The example of the ReAct framework explains in detail the flow of generating the final response by repeating the "Thought (thinking) → Action (tool execution) → Observation (result confirmation)" process.
    - Methods for handling external tools
        - Extensions
            - [[Vertex AI]] provides a mechanism, a standardized interface for agents to directly call and interact with external APIs.
            - By teaching API arguments (parameters) and usage examples to agents, they can spontaneously determine and execute the most appropriate API call.
        - Functions（[[Function Calling]]）
            - The design is such that only "function names and arguments to be called" are proposed on the agent side, and the actual API calls are made on the application (client) side.
            - Useful for authentication, security, batch execution, and cases where the front end intervenes first.
            - As an example, the agent calls the function "display_cities" and returns the parameters in JSON format. The flow is then described in which the client side makes API calls and performs additional processing.
        - Data Stores
            - The RAG (Retrieval Augmented Generation)-like design utilizes a vector database to search and reference external documents as required by the user's query.
            - Incorporate the latest information and documents that are not in the model's training data to increase the accuracy and freshness of responses.



[Building effective agents \ Anthropic](https://www.anthropic.com/research/building-effective-agents)

[AI Agent Evaluation｜Weights & Biases Japan](https://note.com/wandb_jp/n/nf563ea9d3096?sub_rt=share_pb)

[The Shift from Models to Compound AI Systems – The Berkeley Artificial Intelligence Research Blog](https://bair.berkeley.edu/blog/2024/02/18/compound-ai-systems/)

---
This page is auto-translated from [/nishio/AIエージェント](https://scrapbox.io/nishio/AIエージェント) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.