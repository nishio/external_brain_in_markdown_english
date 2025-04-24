---
title: "Creating a system in which humans do not become the bottleneck"
---

<img src='https://scrapbox.io/api/pages/nishio-en/o1 Pro/icon' alt='o1 Pro.icon' height="19.5"/>
Summary: The
Combining UI operation automation with [[Computer Use in Claude]] for tools that do not support the API ([[o1 Pro]]), the need for direct human operation is reduced, and the entire operation is AI-centric. Minimize human involvement by having AI centrally grasp the task management and execution flow, and automate external tools such as o1 Pro in conjunction with management tools such as [[Notion AI]].

Approaches: (1)
- Centralized Task Management:.
    - Consolidate tasks with Notion AI and similar tools.
    - AI performs task detailing, prioritization, and status management.
- Automation of external tool operations:.
    - Tools that do not support APIs, such as o1 Pro, are operated in an RPA-like manner using the Computer Use API.
    - When AI receives commands such as "input data in o1 Pro" or "execute process in o1 Pro," it mimics GUI operations via automated scripts.
    - This allows routine processing (data extraction, writing, button operations, etc.) within o1 Pro to be performed without human intervention.
- Process flow example:.
    - Task registration: When a task is generated in Notion AI, enter "Register new project in o1 Pro" in natural language.
    - AI instruction generation: AI analyzes task content and automatically generates operation scenarios (open window, click menu, enter field, save, etc.) to pass to Computer Use API.
    - Execution and Feedback: The Computer Use API actually operates o1 Pro. Upon completion, the results (success/failure) are reported to the AI, and the task is automatically updated to "completed" by Notion.
- Progress monitoring and adaptation:.
    - All task progress is visualized on Notion, and AI detects delays and errors.
    - When AI detects a problem, prompt scripts are modified and improved for more stable automation.
- Effects
    - Human operation of tools and task organization are no longer required, eliminating human bottlenecks.
    - AI manages all tasks and automates external tool operations, improving work processing speed and accuracy.


# ver.2
Summary: The
Notion AI provides information centralization and advanced task management, and o1 Pro (a non-API tool) uses the Computer Use API to automate GUI operations, thereby restructuring the operational flow to minimize human intervention. Repetitive operations on o1 Pro are fully automated via the Computer Use API. As a result, humans can focus on review and strategic decisions, eliminating the "human bottleneck" situation.

Design points: 1.
- Task centralization (using Notion AI)
    - Knowledge base development: Project information, specifications, and logs are consolidated in Notion.
    - AI Q&A/Summarization: AI instantly summarizes and answers past tasks and documents, reducing human time spent searching for information.
    - Task decomposition and scheduling: AI automatically subdivides broad tasks into smaller ones and manages priorities and deadlines autonomously.
- Automatic operation of non-API tools (o1 Pro) (Computer Use API utilization)
    - Automated GUI operations: Computer Use API performs routine tasks such as logging into o1 Pro, entering fields, and operating buttons in an [[RPA]] manner.
    - Example workflow:.
        - Notion generates "Register a case in o1 Pro" task.
        - Notion AI organizes task content (required data, deadlines)
        - AI generates execution instructions (click position, input content) for Computer Use API
        - Actual operation of o1 Pro with Computer Use API
        - Returns results to Notion and automatically updates task status
- Establishment of [agent loop
    - Iterative process: AI-driven automatic repetition of the cycle of task confirmation → o1 Pro operation → result confirmation.
    - Result analysis and feedback: AI evaluates completed tasks and operation results, and automatically executes error handling and prompt improvements.
- Risk Mitigation and Optimization
    - Security measures: Computer Use API running on a dedicated VM/container, no access privileges or confidential information disclosed.
    - Improved prompts: screenshot confirmation and step-by-step progress check procedures clearly stated to ensure reliability.
    - Periodic Review: Humans regularly review AI operation logs and correct problems with prompts and flows.
- effect
    - Reduced human workload: No manual o1 Pro operation or information organization is required.
    - Fast Decision-Making: Notion AI quickly aggregates information and reduces rework with Q&A capabilities.
    - Scalable: Processing capacity can be expanded without increasing manpower.

Such a design, combined with knowledge and task management based on Notion AI and automatic GUI operation using the Computer Use API, minimizes human intervention, thereby eliminating bottlenecks and significantly improving operational efficiency.

[[The human side is going to be the bottleneck.]]

---
This page is auto-translated from [/nishio/人間がボトルネックにならない仕組みづくり](https://scrapbox.io/nishio/人間がボトルネックにならない仕組みづくり) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.