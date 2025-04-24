---
title: "Long Context vs. RAG for LLMs: An Evaluation and Revisits"
---

[https://arxiv.org/abs/2501.01880](https://arxiv.org/abs/2501.01880)
<img src='https://scrapbox.io/api/pages/nishio-en/o1 Pro/icon' alt='o1 Pro.icon' height="19.5"/>
The first half of the paper systematically surveys several studies dealing with LC and RAG and summarizes what conclusions and claims each study makes, including a list. For example,
- LC is superior to RAG: The claim that LC is stronger than RAG because all documents can be entered at once, especially when a "coherent context" is valid, such as narrative/long-reading comprehension.
- RAG is superior to LC: The claim is that it extracts only the essentials, so performance is not reduced even with long sentences with miscellaneous noise, and furthermore, it saves the computational cost (number of tokens) of the model.
- Combining the two: Some studies conclude that hybrid methods are better, for example, "using more retriever as needed" even in long-context models.
However, it is also noted that there are discrepancies in conclusions among previous studies due to (1) the models and parameter sizes used, (2) the types of data sets and document lengths used, and (3) differences in evaluation methods.


3. creation of evaluation dataset and methodology
- 3.1 Filtering questions
    - The QA data sets used in many studies contain a mixture of questions that could originally be answered only with parametric knowledge of LLM. Such questions that "can be answered without reading external documentation" may prevent a pure comparison of the performance improvement due to RAG and LC.
    - Therefore, the authors asked questions to a large language model (a type of GPT-4) and eliminated questions that could be answered correctly without external context. In this way, only "questions that absolutely require external documentation" are left to allow for fair comparisons.
- 3.2 Expansion of questions
    - Existing data sets have a small number of questions, often only 100-200 questions. Since it is difficult to make statistically adequate comparisons with this level of data, the authors expanded the data in the following way to build a large QA set with approximately 20,000 questions or more.
    - Additional questions and context (including dummy sentences) are collected from the original data source (Wikipedia, novels, etc.).
    - Some datasets are processed to synthetically lengthen documents so that LLM behavior can be tested when given longer sentences.
- 3.3 Typical datasets used in the experiment
    - The paper will employ 12 different QA datasets, including the following: a Wikipedia-based knowledge system, a multi-hop inference system dealing with multiple documents, a reading system from a long story or article, and many other variations.

4. evaluation framework
- The authors' evaluation is divided into the following three levels
    - Phase 1: Retriever (search module) comparison experiment
        - We compared BM25 (sparse), Contriever (dense vector), OpenAI Embeddings, Llama-Index (Index type), and RAPTOR (summary type) as representative search methods, and investigated which retriever is most promising.
        - The experiment concluded that "[[RAPTOR]]" exhibited the highest overall performance.
            - The summary-based RAPTOR showed the best correct response rate (38.5%, etc.), followed by the Llama-Index tree structure approach, while traditional (or simple) chunk segmentation types such as BM25 fared slightly worse, failing to pick up information scattered throughout the long text.
    - Phase 2: Performance comparison of RAG vs. LC
        - Using the best retriever (RAPTOR) selected in Phase 1, the RAG pipeline and LC model (a model where all documents are entered in batches) were compared on a large QA set.
        - Overall, LC had a higher percentage of correct responses (about 56% vs. 49%).
            - However, in about 10% of all cases, "only RAGs reach the correct answer," and there are certainly scenarios where RAGs' unique strengths can be seen.
            - By dataset, LC is strong in areas where "one context is large and cohesive," for example, stories and long sentences derived from Wikipedia.
            - On the other hand, RAGs sometimes showed dominance in data sets that dealt with multiple fragmented dialogue logs or fragmented documents.
    - Phase 3 (Case Analysis)
        - In many cases where LC fails and RAG can get the answer correct, the pattern is that "the context is fragmentary, such as in a conversational style, and the answer can be picked up more accurately by local extraction in RAG.
        - There are many cases where the RAG fails and the LC is correct: "Information related to the question spans multiple paragraphs," "The RAG's chunking tends to break up the information," and "The retriever failed to pick up the information correctly.
        - When visualizing the performance by document type and question type (factual questions such as "Who" and "Where" or explanatory questions such as "How" and "Why"), LC is strong for "questions that require reading or reading long sentences at once" and "questions that require searching and summarizing scattered information" and "Yes/No questions". When visualizing the performance by document type and question type (factual questions such as "Who" and "Where" or explanatory questions such as "How" and "Why"), it is clear that LC is stronger for "questions that require reading or reading long sentences at once," while RAG tends to win for "questions that require searching and summarizing scattered information" and "simple responses such as Yes/No type. The results showed a clear trend.

[[Long Context]] vs. [[RAG]]

---
This page is auto-translated from [/nishio/Long Context vs. RAG for LLMs: An Evaluation and Revisits](https://scrapbox.io/nishio/Long Context vs. RAG for LLMs: An Evaluation and Revisits) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.