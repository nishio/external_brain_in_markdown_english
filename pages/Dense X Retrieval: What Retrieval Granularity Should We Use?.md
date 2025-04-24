---
title: "Dense X Retrieval: What Retrieval Granularity Should We Use?"
---

With respect to [[granularity of RAG]], the approach is to extract "propositions" that can be understood without context by replacing directive words, etc., to create an embedding of propositional units.

> Dense X Retrieval: What Retrieval Granularity Should We Use?
> Tong Chen, Hongwei Wang, Sihao Chen, Wenhao Yu, Kaixin Ma, Xinran Zhao, Hongming Zhang, Dong Yu
> Dense retrieval has become a prominent method to obtain relevant context or world knowledge in open-domain NLP tasks. When we use a learned dense retriever on a retrieval corpus at inference time, an often-overlooked design choice is the retrieval unit in which the corpus is indexed, e.g. document, passage, or sentence. We discover that the retrieval unit choice significantly impacts the performance of both retrieval and downstream tasks. Distinct from the typical approach of using passages or sentences, we introduce a novel retrieval unit, proposition, for dense retrieval. Propositions are defined as atomic expressions within text, each encapsulating a distinct factoid and presented in a concise, self-contained natural language format. We conduct an empirical comparison of different retrieval granularity. Our results reveal that proposition-based retrieval significantly outperforms traditional passage or sentence-based methods in dense retrieval. Moreover, retrieval by proposition also enhances the performance of downstream QA tasks, since the retrieved texts are more condensed with question-relevant information, reducing the need for lengthy input tokens and minimizing the inclusion of extraneous, irrelevant information.
[https://arxiv.org/abs/2312.06648](https://arxiv.org/abs/2312.06648)

<img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/>
- In document retrieval, it is clear that the granularity of the retrieval unit (document, sentence, proposition, etc.) has a significant impact on retrieval performance.
- Instead of the conventional document or sentence unit, a proposition is proposed as a new search unit. A proposition is the smallest unit of expression that represents a fact in a sentence.
- FACTOIDWIKI, which indexes Wikipedia at three granularities: 100-word documents, sentences, and propositions.
- Six different retrieval models were evaluated on five QA datasets, with propositional unit retrieval performing better than document or sentence unit retrieval.
- In particular, propositional unit retrieval was greatly superior in domains not included in the training data of the retrieval model.
- In the QA task, propositional unit search achieved the highest accuracy under the same token count restriction.
- Propositions are rich in contextual information, albeit in a compressed form, and thus are expected to have a higher density of question-related information.
- We hope that the findings of this research and FACTOIDWIKI will contribute to the development of information retrieval.

![image](https://gyazo.com/ee2dd5043850ffe30038c6eb0f9d86e9/thumb/1000)
[[Proposition indexing]]

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>How do you index a proposition?

<img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/>The specific steps to index a proposition are as follows
- Divide each Wikipedia page into paragraphs.
- To split each paragraph into propositions, the GPT-4 is used to create a dataset for propositional splitting.
    - Prompt GPT-4 to convert a paragraph into a list of propositions.
    - Collection of over 40,000 pairs of paragraph and propositional listings.
- The collected dataset is used to train a propositional partitioning model (Propositionizer).
    - Flan-T5-Large is used as the base model.
    - Fine-tuned to enter a paragraph and output a list of propositions.
- Split all Wikipedia pages into propositions using the learned Propositionizer.
    - Convert each paragraph into a list of propositions.
    - Ultimately, more than 250 million propositions are generated.
- Index the divided propositions.
- Use [[pyserini]] and [[faiss]] libraries.
- Each proposition is converted to an embedded vector in a batch process.
- Vectors are indexed to enable efficient approximate nearest neighbor search.
- When searching, the query is converted into an embedded vector, and the index is searched to efficiently retrieve relevant propositions.

With the above procedure, FACTOIDWIKI can be constructed, indexing all pages of Wikipedia on a proposition-by-proposition basis. For indexing large propositions, parallelization of GPUs and distributed indexing are also utilized to accelerate online searches.

So you create teacher data with GPT4, train a model on that data, and then use it to process all the pages of Wikipedia?<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>


<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>"Convert a paragraph to a list of propositions by prompting GPT-4" more here

<img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/>The procedure for converting a paragraph into a list of propositions using GPT-4 is as follows
- Create a prompt that clearly defines the proposition and how it is to be split. For example, use the following prompt.
    - Use the following procedure to divide the given paragraph into a clear and simple list of propositions.
    - Split compound sentences into single sentences. Maintain the original expression as much as possible.
    - If there is additional information in the noun phrase, it is split into independent propositions.
    - Decontextualize] the proposition, e.g., by replacing the pronoun with the noun to which it refers.
        - I see.<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
            - It would be easy to take the facts [[out of context]] and make them [[atomic]], but is that generally the case?
                - Some activities, like [[Fireworks to think about]], are a mesh of what was originally separated
    - Output the results as a list in JSON format.
- After the prompt, give as input the Wikipedia paragraph you want to split into propositions.
- Give GPT-4 a prompt and an input paragraph and have it generate a list of propositions.
- Review the list of propositions generated and make manual corrections as necessary.
- Repeat steps 2-4 until a proposition list of sufficient quality is obtained.
- The following is an actual prompt and example output.

![image](https://gyazo.com/3a0ab713a473485e7afbba4beecdb5a6/thumb/1000)

This procedure was performed on more than 40,000 paragraphs to create a dataset consisting of pairs of paragraphs and propositional lists. This large data set enabled us to effectively train the [[propositional partitioning model]].

---
This page is auto-translated from [/nishio/Dense X Retrieval: What Retrieval Granularity Should We Use?](https://scrapbox.io/nishio/Dense X Retrieval: What Retrieval Granularity Should We Use?) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.