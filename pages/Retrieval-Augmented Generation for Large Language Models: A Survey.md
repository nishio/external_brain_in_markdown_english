---
title: "Retrieval-Augmented Generation for Large Language Models: A Survey"
---

[2312.10997 Retrieval-Augmented Generation for Large Language Models: A Survey](https://arxiv.org/abs/2312.10997)
<img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/>This is a comprehensive survey paper on Retrieval-Augmented Generation ([[RAG]]) techniques that improve the performance of large-scale language models (LLMs). The main contents of the paper are as follows.

1. the development of RAG can be categorized into three paradigms: Naive RAG, [[Advanced RAG]], and [[Modular RAG]]. Each has been developed to overcome the limitations of the previous paradigm.
- The three foundational components of the RAG framework are Retrieval, Generation, and Augmentation. State-of-the-art technologies in each component are examined in detail.
3. the main downstream tasks of RAGs and the state-of-the-art evaluation frameworks and benchmarks for evaluating them are presented.
4. RAGs currently face several challenges, but future R&D directions include improving robustness, adapting to longer contexts, and extending to multimodal.
5. RAG technology can significantly improve the capacity of LLMs by synergistically integrating parametric knowledge and non-parametric external databases.

RAG technology is developing rapidly and is attracting significant attention from academia and industry. It is expected to have a significant impact on the future development of the AI field.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>What problems does Advanced RAG solve?

<img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/>Advanced RAG is a method developed to overcome the limitations of Naive RAG. Specifically, it solves the following problems
1. improve the quality of search:
    - In the pre-retrieval phase, the index structure and the original query are optimized to improve the accuracy and reproducibility of the retrieval. For example, increasing the granularity of data, optimizing the index structure, adding metadata, and rewriting or transforming the query are used.
    - In the post-retrieval stage, retrieved information is re-ranked based on relevance and important information is selected and compressed to improve the quality of the context to be passed to the generation stage.
2. improvement of the quality of generation:
    - Instead of inputting retrieved information directly into the language model, rearrange the information according to its importance and delete unnecessary information to improve the quality of the responses generated. In addition, fine-tuning the language model specific to the task will enable more appropriate responses to be generated.
3. efficiency of the expansion phase:
    - When integrating retrieved information, remove duplicate information or convert it to a format more appropriate for the task, thereby increasing the efficiency of the expansion phase. In addition, search and generation should be iterative so that more appropriate answers can be generated for complex problems.

By combining these methods, Advanced RAG aims to comprehensively solve the problems of Naive RAG and improve the performance of the entire RAG system.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>What improvements in pre-retrieval can be made?

<img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/>Pre-retrieval improvements include the following techniques

1. optimization of index structure:
- - Build a hierarchical index structure to enable quick retrieval of relevant information.
- - Knowledge graphs are used to represent relationships between documents to improve search accuracy.

Optimization of chunk partitioning:
- - Semantic integrity is maintained by dividing documents at sentence boundaries rather than by fixed-length token counts.
- - Allow overlap between chunks using the sliding window method to prevent missing context.

Add metadata:
- - Document metadata (page number, file name, author, category, timestamp, etc.) is assigned to the chunk and used for filtering when searching.
- - Bridging the semantic gap between questions and answers by adding artificial metadata such as summaries and hypothetical questions.

4. query optimization:
- - Expanding on multiple queries complements context that cannot be captured by a single query.
- - Improve search accuracy by breaking down complex queries into sub queries.
- - Rewrite the query using LLM to convert it into a format suitable for searching.
- - Use step-back prompting to abstract queries to allow for more extensive searches.

5. query routing:
- - Select appropriate search methods and search targets based on query metadata and semantic information.
- - Combine multiple search methods to increase the comprehensiveness of the search.

The right combination of these techniques can improve the accuracy and efficiency of searches and provide higher quality context for the generation phase.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
Why does building a [[hierarchical indexing structure]] allow for quick retrieval of relevant information?
- How exactly does [[knowledge graph]] work?
- Learn more about the use of [[summary]].
How do we [[decompose]] a query into [[secondary queries]]?
What is [[step-back prompting]]?

<img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/>
1. why building a hierarchical index structure allows for quick retrieval of relevant information:
- - Documents can be organized by parent-child relationship and chunks can be associated with them to narrow down the search target.
- - Storing a [[summary]] of the data at each node provides a quick overview of the data and makes it easier to determine which chunks should be retrieved.
- - By following a hierarchical structure, related chunks can be searched efficiently.

2. specific uses of the knowledge graph:
- - Explicitly expressing relationships between different concepts and entities can maintain contextual coherence and reduce hallucination.
- - Translating the information retrieval process into instructions that LLMs can understand improves the accuracy of knowledge retrieval and enables the generation of contextualized answers.
- - When building an index among multiple documents, the knowledge graph can be used to capture the logical relationships between document content and structure.

3. the use of summaries:
- - Adding document summaries as artificial [[metadata]] can bridge the semantic gap between questions and answers.
- - The summary can be used for filtering when searching to improve the accuracy of the search.
- - Recursive search] based on summaries allows efficient processing of long documents and PDFs with complex structures.

4. how to decompose a query into sub queries:
- - Decompose a complex query into the simpler sub-queries that make it up.
- - Derive an answer to the original query by combining secondary queries.
- - For decomposition, use the [[LEAST-TO-MOST PROMPTING METHOD]] or other methods.

5. what is step-back prompting?
- - A technique that abstracts the original query to generate a high-level conceptual question ([[step-back question]]).
- - The RAG system uses both the step-back question and the original query in the search and uses the results as the basis for generating answers in the language model.
- - Generating more abstract questions broadens the scope of the search and allows for more comprehensive information to be obtained.

The proper combination of these methods can improve the efficiency of the RAG system's search and the quality of the responses it generates.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
What is a recursive search based on a summary?
What is the least-to-most prompting method?

<img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/>
1. recursive search based on summaries:
- This technique is useful for processing long documents and PDFs with complex structures. It is performed in the following steps
    - a) Process and search a portion of a document (e.g., a section or page) using a structured index.
    - b) Create a summary of the retrieved portion.
    - c) Based on that summary, conduct a more detailed search within the document.

- This recursive, summary-based search allows for step-by-step refinement of large amounts of information. It may also be combined with multi-hop search to extract more deeply relevant information from graph-structured data sources.

2. least-to-most prompting method:
- This technique is used to decompose a complex question into a series of simpler sub-questions. It is done in the following steps

    - a) Receive complex questions.
    - b) Break the question down into simpler, more specific sub-questions.
    - c) Secondary questions are in turn entered into the language model to generate answers.
    - d) Combine the generated answers to derive the final answer to the original complex question.

- For example, "What were the primary causes of World War II?" can be broken down into the following sub-questions
    - - When did World War II occur?
    - - Which major countries participated in World War II?
    - - How did the rise of Nazi Germany cause World War II?
    - - How did the Japanese invasion cause World War II?

- By answering these sub-questions in turn, a comprehensive answer to the original complex question can be generated.

- Using the least-to-most prompting method, complex questions can be converted into a more manageable format and take full advantage of the language model's capabilities.
---
This page is auto-translated from [/nishio/Retrieval-Augmented Generation for Large Language Models: A Survey](https://scrapbox.io/nishio/Retrieval-Augmented Generation for Large Language Models: A Survey) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.