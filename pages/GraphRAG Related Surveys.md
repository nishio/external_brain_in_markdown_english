---
title: "GraphRAG Related Surveys"
---

2025-09-04

<img src='https://scrapbox.io/api/pages/nishio-en/GPT5/icon' alt='GPT5.icon' height="19.5"/>
1) What to extract (type of extraction target)
A. Basic three-piece set
- Entity / Relation / Event (Event): unique expressions within and between documents, relational links, events + roles.
    - Typical extractors include [[DyGIE++]], [[OneIE]], [[OpenIE]] systems (OpenIE5/6), and [[REBEL]] in [[Generative Relation Extraction]].
    - These are used to create the skeleton of the [[knowledge graph]].
    - ([arXiv](https://arxiv.org/pdf/1909.03546?utm_source=chatgpt.com), [ACL Anthology](https://aclanthology.org/2020.acl-main.713.pdf?utm_source=chatgpt.com))
B. Time, causality, and time series
- Extraction of temporal relationships (before/after/simultaneous) and event causality.
- Used to construct timelines and causal graphs across documents.
- Effective for long and long histories, such as medical. ([arXiv](https://arxiv.org/abs/2104.09570?utm_source=chatgpt.com), [ScienceDirect [https://www.sciencedirect.com/science/article/pii/S](https://www.sciencedirect.com/science/article/pii/S) 0950705124000455?utm_source=chatgpt.com], [PMC](https://pmc.ncbi.nlm.nih.gov/articles/PMC11105141/?utm_source=chatgpt.com), [ACL Anthology](https://aclanthology.org/2024.findings-emnlp.986.pdf?utm_source=chatgpt.com))
C. Arguments, Claims, and Grounds (Provnance)
- Graphs of claims/refutations/evidence ([[Argument Interchange Format]]: AIF) and [[W3C PROV]] of the source and generation process are assigned.
- It works for accountability, verification, and reproduction of answers.
- ([Wikipedia](https://en.wikipedia.org/wiki/Argument_Interchange_Format?utm_source=chatgpt.com), [Centre for Argument Technology](https://www.arg-tech.org/wp-content/uploads/2011/09/aif-spec.pdf?utm_source=chatgpt.com), [W3C](https://www.w3.org/TR/prov-overview/?utm_source=chatgpt.com))
D. Core reference and normalization
- Entity identity resolution (alias/abbreviation/notation shaking) and linking (e.g., Wikidata).
- Directly related to the consistency and search reproducibility of the knowledge graph (essential pre-processing for implementation).

2) How to use (processing patterns using graph/DAG)
(1) Search/RAG (graph-guided)
- [[GraphRAG]]: Create KG ([[Knowledge Graph]]) from a set of documents and pre-calculate Community Detection -> [[Hierarchical Summary]].
    - Responds to questions with local search (surrounding subgraphs + source text chunks) and global search (across communities and reports) or [[DRIFT]] (a combination of both). Strong on "big picture" type questions. ([Microsoft GitHub](https://microsoft.github.io/graphrag/?utm_source=chatgpt.com), [Microsoft [https://www.microsoft.com/en-us/research/](https://www.microsoft.com/en-us/research/) blog/graphrag-new-tool-for-complex-data-discovery-now-on-github/?utm_source=chatgpt.com])
- [[HippoRAG]]: Aiming for multi-stage inference class accuracy even with single-stage acquisition using Personalized PageRank on KG to expand related nodes (up to 20% improvement reported by [[HotpotQA]] and others). Contributes to improved efficiency of multi-leap queries and search. ([arXiv](https://arxiv.org/abs/2405.14831?utm_source=chatgpt.com))
- [[LightRAG]] / [[LlamaIndex-KG]]: A lightweight implementation system that turns a triplet extraction → subgraph RAG.
    - Suitable for integration of proprietary graphs and for "low-cost graphs in combination.
    - ([lightrag.github.io](https://lightrag.github.io/?utm_source=chatgpt.com), [arXiv](https://arxiv.org/abs/2410.05779?utm_source=chatgpt.com), [LlamaIndex](https://docs.llamaindex.ai/en/stable/api_reference/indices/knowledge_graph/?utm_source=chatgpt.com))
- [[G-Retriever]] / [[GRAG]]: Specialized in graph QA, GNN + LLM + RAG for fast and accurate giant graph QA.
    - For GraphQA and KBQA for research purposes. ([NeurIPS Proceedings [https://proceedings.neurips.cc/paper_files/paper/2024/file/efaf1c9726648c8ba363a5c927440529-Paper-Conference.](https://proceedings.neurips.cc/paper_files/paper/2024/file/efaf1c9726648c8ba363a5c927440529-Paper-Conference.) pdf?utm_source=chatgpt.com], [ACL Anthology](https://aclanthology.org/2025.findings-naacl.232.pdf?utm_source=chatgpt.com))
- SURVEY: An overview of GraphRAG's standard workflow (G-Indexing -> G-Retrieval -> G-Generation). Recommended reading before implementation. ([arXiv](https://arxiv.org/abs/2408.08921?utm_source=chatgpt.com))
(2) Summary and overall understanding
- [[GraphRAG]] (QFS oriented): Scale query-focused summarization with a combination of KG + community summarization.
    - For cross-company reports and extracting themes from huge corpora. ([arXiv](https://arxiv.org/abs/2404.16130?utm_source=chatgpt.com))
- [[RAPTOR]]: Build a cluster -> [[Hierarchical Summary Tree]] (Tree) and pull from the appropriate level when searching.
    - Hierarchical summary index for DAG/tree systems. ([arXiv](https://arxiv.org/abs/2401.18059?utm_source=chatgpt.com))
(3) Agent/dialog memory
    - [[Theanine (memory system)]]: does not assume memory deletion. Timelines past events with time/causality links and injects **"transition of events/causality "** as context into response generation. Also presented the evaluation framework TeaFarm (NAACL 2025). Specializes in preserving the context of long-term dialogues. ([arXiv](https://arxiv.org/abs/2406.10996))
- [[MemGPT]] / [[LongMem]]: direction to handle long history in memory hierarchy and virtual context management (memory OS/banks rather than graphs); complementary to Theanine's time and causality graphs. ([arXiv](https://arxiv.org/abs/2310.08560?utm_source=chatgpt.com), [NeurIPS Proceedings [https://proceedings.neurips.cc/paper_files/](https://proceedings.neurips.cc/paper_files/) paper/2023/file/ebd82705f44793b6f9ade5a669d0f0bf-Paper-Conference.pdf?utm_source=chatgpt.com])
4) Verification, explanation and consistency check
- The PROV holds the edges of the origin (who/what/when generated), and the evidence path is presented when responding; the AIF holds the argument graph of claim - evidence - counterargument, allowing the user to say "why this is so"; and the AIF holds the argument graph of claim - evidence - counterargument, allowing the user to say "why this is so". ([W3C](https://www.w3.org/TR/prov-overview/?utm_source=chatgpt.com), [Wikipedia [https://en.wikipedia.org/wiki/Argument_Interchange_](https://en.wikipedia.org/wiki/Argument_Interchange_) Format?utm_source=chatgpt.com])

3) Comparison of representative approaches (to the point)
_
| Strain Main extraction Structure used Strengths/uses (key points) |
| -- |
| GraphRAG (Microsoft) KG extraction with LLM + community detection -> hierarchy summary KG + hierarchy (global/local/DRIFT) Strong overall and multi-document QFS. Full operational guidance and implementation. ([Microsoft GitHub https://microsoft.github.io/graphrag/?utm_source=chatgpt.com], [Microsoft https://www.microsoft.com/en-us/research/ blog/graphrag-new-tool-for-complex-data-discovery-now-on-github/?utm_source=chatgpt.com]) |
| HippoRAG Entity/Relationship KG + Personalized PageRank Low cost high accuracy with multi-leap QA. Strong even for single-stage acquisition. ([arXiv https://arxiv.org/abs/2405.14831?utm_source=chatgpt.com]) |
| LightRAG Triple Extraction Lightweight KG + K/V index Easy setup, low latency. ([lightrag.github.io https://lightrag.github.io/?utm_source=chatgpt.com], [arXiv https://arxiv.org/abs/2410.05779?utm_source=chatgpt. com]) |
| LlamaIndex-KG Triplet Extraction Subgraph RAG Easy to configure to add a KG retriever to an existing RAG. ([LlamaIndex https://docs.llamaindex.ai/en/stable/api_reference/indices/knowledge_graph/?utm_source=chatgpt.com]) |
| Theanine Dialogue memory fragments Timeline linked by time and causality Long-term dialogue to understand the "history of change" and reflect it in responses. ([arXiv https://arxiv.org/abs/2406.10996]) |
| RAPTOR Embedded -> Cluster Hierarchical summary tree (Tree/DAG) Search huge corpus step by step from top concepts. ([arXiv https://arxiv.org/abs/2401.18059?utm_source=chatgpt.com]) |
| G-Retriever/GRAG graph QA assumption GNN + LLM + RAG Giant graph QA for high speed/high accuracy. ([NeurIPS Proceedings https://proceedings.neurips.cc/paper_files/paper/2024/file/efaf1c9726648c8ba363a5c927440529-Paper-Conference. pdf?utm_source=chatgpt.com], [ACL Anthology https://aclanthology.org/2025.findings-naacl.232.pdf?utm_source=chatgpt.com] |





4) Implementation intuition (design patterns)
(a) Data model design
- Property Graph or RDF: Ease of query (Cypher) or standard vocabulary/interoperability (RDF/OWL, PROV-O)? It is easier to attach the source/generation process with PROV from the beginning. ([W3C](https://www.w3.org/TR/prov-overview/?utm_source=chatgpt.com))
- Node type design: `Entity / Event / Claim / Source / Community / Memory`, etc. Time (occurrence / observation / validity period) and causality are primary class citizens.
- ID and identification: core reference integration (separate descriptions of the same person/organization). Paying the cost of knowledge maintenance in the initial phase stabilizes multi-jump searches in the later stages.
(b) Extraction pipeline (minimum configuration)
1. segmentation (paragraph/sentence/speech) → language preprocessing (NER, co-ref)
2. relation/event extraction: REBEL/OneIE/DyGIE++ etc. or LLM-guided triad extraction (cost⇆precision tradeoff). ([ACL Anthology](https://aclanthology.org/2021.findings-emnlp.204.pdf?utm_source=chatgpt.com), [arXiv [https://arxiv.org/pdf/1909.03546?](https://arxiv.org/pdf/1909.03546?) utm_source=chatgpt.com])
3. time/causality link: extract event time/sequence/causality (rules + LLM or existing methods) ([arXiv](https://arxiv.org/abs/2104.09570?utm_source=chatgpt.com))
4. normalization/identification (KB link, dictionary, embedding)
5. storage (Graph DB / RDF store) + dual index (vector & graph)
6. (Optional) Hierarchical: GraphRAG community detection -> report generation, pre-calculation of RAPTOR hierarchical summary tree. ([Microsoft [https://www.microsoft.com/en-us/research/blog/graphrag-new-tool-for-complex-data-discovery-now-on-github/?utm_source=](https://www.microsoft.com/en-us/research/blog/graphrag-new-tool-for-complex-data-discovery-now-on-github/?utm_source=) chatgpt.com], [arXiv](https://arxiv.org/abs/2401.18059?utm_source=chatgpt.com))
(c) Manner of Retrieval
- Local: seed node from question and neighborhood expansion + source text chunks together (GraphRAG: Local). ([Microsoft GitHub](https://microsoft.github.io/graphrag/?utm_source=chatgpt.com))
- Global: synthesis across community summaries (GraphRAG: Global/DRIFT). Works for theme-based questions. ([Microsoft [https://www.microsoft.com/en-us/research/blog/graphrag-improving-global-search-via-dynamic-community-selection/?utm_](https://www.microsoft.com/en-us/research/blog/graphrag-improving-global-search-via-dynamic-community-selection/?utm_) source=chatgpt.com])
- Ranking: hybrid PPR/short path/centricity and embedding similarity; PPR is the key to HippoRAG (good starting point for implementation). ([arXiv](https://arxiv.org/abs/2405.14831?utm_source=chatgpt.com))
(d) Generation
- Pass "structure" to the prompt: subgraph (nodes/edges/provenance) + minimal source text.
- Hierarchical summary synthesis: GraphRAG's step-by-step synthesis of community report -> partial response -> final summary is less likely to break down even at large scale. ([arXiv](https://arxiv.org/abs/2404.16130?utm_source=chatgpt.com))
(e) Memory (dialogue/agent)
- Theanine style: Present necessary parts from a timeline linked by time and causality without deleting memory. MemGPT/LongMem is supplemented by overflow history storage (hierarchical memory). ([arXiv](https://arxiv.org/abs/2406.10996), [NeurIPS Proceedings [https://proceedings.neurips.cc/paper_files/paper/2023/file/ebd82705f](https://proceedings.neurips.cc/paper_files/paper/2023/file/ebd82705f) 44793b6f9ade5a669d0f0bf-Paper-Conference.pdf?utm_source=chatgpt.com])
(f) Evaluation
- QA/Summary: Accuracy (EM/F1), inclusiveness/diversity (e.g., QFS settings for GraphRAG articles). ([arXiv](https://arxiv.org/abs/2404.16130?utm_source=chatgpt.com))
- Memory integration understanding: see if you can really use "past event transitions" with a counterfactual test like Theanine's TeaFarm. ([arXiv](https://arxiv.org/abs/2406.10996))
(g) Risks and countermeasures
- Extraction illusions: LLM extraction produces false links/over-abstraction. Mitigate by two-step extraction (candidate -> validation) or source-required.
- Renewal and Drift: designing incremental renewal of new documents and recalculation strategies for old summaries/communities; GraphRAG adjusts cost/quality by switching between global/local/DRIFT. ([Microsoft [https://www.microsoft.com/en-us/research/blog/introducing-drift-search-combining-global-and-local-search-methods-to-](https://www.microsoft.com/en-us/research/blog/introducing-drift-search-combining-global-and-local-search-methods-to-) improve-quality-and-efficiency/?utm_source=chatgpt.com])

5) First, implementation templates (minimum configuration)
1. base: vector RAG (embedding + preservation of original text).
2. KG Combination: generate and store triples in LlamaIndex KnowledgeGraphIndex (can be Neo4j or RDF). At the same time, PROV-O is used to connect the sources. ([LlamaIndex](https://docs.llamaindex.ai/en/stable/api_reference/indices/knowledge_graph/?utm_source=chatgpt.com), [W3C [https://www.w3](https://www.w3) .org/TR/prov-overview/?utm_source=chatgpt.com])
3. graph utilization:
    - Local GraphRAG with proximity subgraph + original text. ([Microsoft GitHub](https://microsoft.github.io/graphrag/?utm_source=chatgpt.com))
    - Pre-calculate community detection -> hierarchical summaries as needed (for global and DRIFT questions). ([Microsoft [https://www.microsoft.com/en-us/research/blog/graphrag-new-tool-for-complex-data-discovery-now-on-github/?utm_source=](https://www.microsoft.com/en-us/research/blog/graphrag-new-tool-for-complex-data-discovery-now-on-github/?utm_source=) chatgpt.com])
    - If you have a lot of multiple bounces, install HippoRAG's PPR. ([arXiv](https://arxiv.org/abs/2405.14831?utm_source=chatgpt.com))
4. dialogue memory: event nodes (utterances/actions/preferences) for each user are linked by time and causality to maintain a timeline (Theanine's policy). ([arXiv](https://arxiv.org/abs/2406.10996))

6) Usage guidelines (roughly)
- **ask for "big picture/theme "**: GraphRAG (global/DRIFT) or RAPTOR. ([arXiv](https://arxiv.org/abs/2404.16130?utm_source=chatgpt.com))
- 'Multi-jump QA with few clues': HippoRAG (PPR) -> G-Retriever/GRAG if needed. ([arXiv](https://arxiv.org/abs/2405.14831?utm_source=chatgpt.com), [NeurIPS Proceedings [https://proceedings.neurips.cc/paper_files/paper/2024/file/efaf1c9726648c8ba363a5c927440529-Paper-Conference.pdf?utm_](https://proceedings.neurips.cc/paper_files/paper/2024/file/efaf1c9726648c8ba363a5c927440529-Paper-Conference.pdf?utm_) source=chatgpt.com], [ACL Anthology](https://aclanthology.org/2025.findings-naacl.232.pdf?utm_source=chatgpt.com))
- I want to add KG with low operational cost": LightRAG or LlamaIndex-KG. ([lightrag.github.io](https://lightrag.github.io/?utm_source=chatgpt.com), [[LlamaIndex https ://docs.llamaindex.ai/en/stable/api_reference/indices/knowledge_graph/?utm_source=chatgpt.com]])
- I want to use it without losing the context of the long-term dialogue": theanine time and causal timeline + MemGPT/LongMem as needed. ([arXiv](https://arxiv.org/abs/2406.10996), [[NeurIPS Proceedings https ://proceedings.neurips.cc/paper_files/paper/2023/file/ebd82705f44793b6f9ade5a669d0f0bf-Paper-Conference.pdf?utm_source=chatgpt.com ]])

7) Supplement: Graph-of-Thoughts system (graphing of "thoughts")
The target of extraction is not "external text" but LLM intermediate thoughts, but a system that enhances inference with graph structure (reuse, branching, confluence). It can be used in conjunction with external KG for the framework of inference. ([arXiv](https://arxiv.org/abs/2308.09687?utm_source=chatgpt.com))

Reference and starting point links (excerpts)
- GraphRAG (How it works, implementation, and operations blog) ([Microsoft GitHub](https://microsoft.github.io/graphrag/?utm_source=chatgpt.com), [Microsoft [https://www.](https://www.) microsoft.com/en-us/research/blog/graphrag-new-tool-for-complex-data-discovery-now-on-github/?utm_source=chatgpt.com])
- HippoRAG（NeurIPS'24） ([arXiv](https://arxiv.org/abs/2405.14831?utm_source=chatgpt.com))
- LightRAG ([lightrag.github.io](https://lightrag.github.io/?utm_source=chatgpt.com), [arXiv](https://arxiv.org/abs/2410.05779?utm_source=chatgpt.com))
- LlamaIndex: KnowledgeGraphIndex ([LlamaIndex](https://docs.llamaindex.ai/en/stable/api_reference/indices/knowledge_graph/?utm_source=chatgpt.com))
- Theanine（NAACL'25） ([arXiv](https://arxiv.org/abs/2406.10996))
- RAPTOR（ICLR'24） ([arXiv](https://arxiv.org/abs/2401.18059?utm_source=chatgpt.com))
- GraphRAG Survey（2024） ([arXiv](https://arxiv.org/abs/2408.08921?utm_source=chatgpt.com))

Next Steps (Memo for Practical Use)
- In PoC: 1) Triplet extraction + Subgraph RAG (inexpensive) → 2) Community summary/DRIFT ("big picture" question support) → 3) PPR (multi-jump reinforcement) → 4) Dialogue timeline (long-term memory), in that order of expansion.
- Metrics: mix QA (EM/F1), inclusivity/diversity (QFS systems), counterfactuals (TeaFarm). ([arXiv](https://arxiv.org/abs/2404.16130?utm_source=chatgpt.com))
- Policy: Provnance (source path) on all output. Effective for future audit and observability. ([W3C](https://www.w3.org/TR/prov-overview/?utm_source=chatgpt.com))

If necessary, the data at hand/requirements (corpus size, question patterns, latency budget) will be fleshed out to a minimum configuration blueprint.

[https://chatgpt.com/c/68b7f215-cd4c-8323-b08e-f107d41fb58b](https://chatgpt.com/c/68b7f215-cd4c-8323-b08e-f107d41fb58b)

[https://chatgpt.com/c/68ba8b5f-17fc-8327-ba44-bf69ba51856c](https://chatgpt.com/c/68ba8b5f-17fc-8327-ba44-bf69ba51856c)
- [[A Framework for Constructing Concept Maps from E-Books Using Large Language Models: Challenges and Future Directions]]

---
This page is auto-translated from [/nishio/GraphRAG関連サーベイ](https://scrapbox.io/nishio/GraphRAG関連サーベイ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.