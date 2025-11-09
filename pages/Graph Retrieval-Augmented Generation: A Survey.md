---
title: "Graph Retrieval-Augmented Generation: A Survey"
---

from [[GraphRAG]]
[[Graph Retrieval-Augmented Generation: A Survey]]
[https://arxiv.org/abs/2408.08921](https://arxiv.org/abs/2408.08921)
![image](https://gyazo.com/5ab30b83b00a9bd520b88793b9dbe9ce/thumb/1000)
<img src='https://scrapbox.io/api/pages/nishio-en/GPT5/icon' alt='GPT5.icon' height="19.5"/>
A comprehensive review that organizes a system of techniques to compensate for the weaknesses of RAG (ignoring relationships, redundant context, lack of the big picture) by utilizing graph structure (KG/TAG) to achieve more accurate and contextual understanding of the generation.

What's new.
- GraphRAG formulation:
    - 1.[[G-Indexing]] (graph construction and indexing)
    - 2.[[G-Retrieval]] (Retrieval of node/triple/path/subgraph)
    - 3.[[G-Generation]] (Generate acquisition graph as input)
- Utilizes relational knowledge and global structures that are difficult to pick up in string RAGs, and is advantageous in QFS, etc.

G-Indexing (graph infrastructure)
- Data source: open KG (Wikidata/ConceptNet, etc.) / own construction (TAG from documents, tables, logs).
- Index:
    - Graph Indexing (Structure Search)
    - Text index (Template conversion → BM25/dense search)
    - Vector index (node/egonet embedding)
    - Hybrid recommended.

G-Retrieval
- Retrievers: non-parametric (BFS/shortest path/PCST), LM systems, GNN systems, or combined.
- Paradigm: batch/repeat (adaptive/non-adaptive)/multi-stage (coarse to fine).
- Granularity: node, triple, path, subgraph, mixed.
- Enhancement: query expansion/decomposition, knowledge merge/pruning (re-ranking, PageRank, LLM checks, etc.)

G-Generation
- Generator:
    - GNN (strong in discrimination tasks)
    - LM (strong in generation/reasoning)
    - Hybrid: cascade (GNN to LM prefix)/parallel (representation coupling and output integration).
- LM input format for graphs:
    - Graph language (edge tables, natural sentences, code-like notation, syntax trees, node sequences)
    - Graph embedding (fused by Prefix/Prompt Tuning or FiD).
- Generation enhancement: pre (rewriting and planning) / during (constraint decoding, etc.) / post (answer integration and verification).

learning
- No learning required: rule search + prompts, embedded similarity.
- With learning: Supervision/remote supervision/RL/self-supervision to optimize the retriever/generator.
- Collaborative learning: mutual reinforcement for alternate learning and integration purposes.

Application and evaluation
- Tasks: KBQA/CSQA, EL/RE, fact verification, link prediction, dialogue, recommendation.
- Areas: e-commerce, medical, academic, legal, literary, etc.
- Bench: WebQSP/CWQ/HotpotQA, etc., STaRK, GraphQA, GRBENCH, CRAG.
- Indicators: EM/F1/Accuracy/BLEU types + acquisition quality (coverage, diversity, fidelity).

Industry Case Studies
- Microsoft GraphRAG (QFS enhanced with community summary), NebulaGraph Edition, Ant Group Edition, Neo4j NaLLM/Graph Builder, etc.

Future Issues
- Dynamic graph updating and adaptation, multimodal integration, and efficiency in large graphs,
- Linkage with Graph Foundation Models, lossless compression to mitigate long-text problems, standard bench maintenance, and application extensions.

Practical tips (super summary)
- Hybrid indexing + multi-stage acquisition for accuracy/cost optimization even on a small scale.
- Select granularity (path/subgraph center) according to the task.
- LM input should be in short, complete, readable graph language (community summary if necessary).
- Critical phases are stabilized when re-ranking/pruning and post-verification are included.


---
This page is auto-translated from [/nishio/Graph Retrieval-Augmented Generation: A Survey](https://scrapbox.io/nishio/Graph Retrieval-Augmented Generation: A Survey) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.