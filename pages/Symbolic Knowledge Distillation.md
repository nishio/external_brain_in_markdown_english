---
title: "Symbolic Knowledge Distillation"
---

Symbolic Knowledge Distillation: from General Language Models to Commonsense Models
[https://arxiv.org/abs/2110.07178](https://arxiv.org/abs/2110.07178) (2021)
<img src='https://scrapbox.io/api/pages/nishio-en/o3-mini-high/icon' alt='o3-mini-high.icon' height="19.5"/>
This paper proposes a new method, Symbolic Knowledge Distillation, which automatically generates common sense knowledge from a large-scale language model (GPT-3) and creates a high-quality [[common sense knowledge graph]] and a compact and high-performance [[common sense model]] in the following three steps.

1.### Machine to corpus
.
    - GPT-3 is used with Few-shot prompting to generate a large number (ATOMIC10x) of ATOMIC-style common sense events and inferences (e.g., events and their consequences).
        - Although the generated results are higher in quantity and diversity than the manually created ATOMIC20, the quality of the results varies.

2.### Filtering by Critics
.
    - Using a clitic model learned based on human evaluation, the system excludes generated results with logical inconsistencies or unnatural expressions.
        - Filtering strikes a balance between increasing quality while retaining sufficient data volume.

3.### From corpus to model (knowledge distillation)
.
    - A small common sense model (COMETDISTIL) is trained using a filtered knowledge graph.
        - Surprisingly, the student model exhibits higher common sense reasoning performance than the teacher, GPT-3.

This method is unique in that it extends the concept of [[knowledge distillation]] to symbolic text generation and incorporates a small amount of human evaluation, resulting in the construction of a larger and higher quality knowledge resource and more efficient acquisition of common sense models than traditional manually created knowledge graphs.



The following papers present foundational methods in the areas of knowledge acquisition and knowledge graph construction that are useful to know in relation to Symbolic Knowledge Distillation.

- Hinton et al. (2015)
- "[[Distilling the Knowledge in a Neural Network]]"
- → This is a basic method of knowledge distillation that transfers knowledge from a large model to a small model.

- Sap et al. (2019)
- *"[[ATOMIC: An Atlas of Machine Commonsense for If-Then Reasoning]]"*
- → A typical example of a knowledge graph construction method for common sense reasoning, it deals with if-then rules in natural language.

- Bosselut et al. (2019)
- *"[[COMET: Commonsense Transformers for Automatic Knowledge Graph Construction]]"*
- → We propose a Transformer-based approach to automatically generate common sense knowledge graphs, which can be positioned as an advanced form of Symbolic Knowledge Distillation.

- Petroni et al. (2019)
- *"[[Language Models as Knowledge Bases?]]"*
- → The report examines methods for extracting and utilizing knowledge stored inside the language model, which is helpful from the perspective of knowledge acquisition.

- Davison et al. (2019)
- *"[[Commonsense Knowledge Mining from Pretrained Models]]"*
- → Discusses how to effectively extract common sense knowledge from pre-trained models, showing the potential for automatic knowledge acquisition.

Also see ### Speer et al. (2017) "[[ConceptNet 5.5: An Open Multilingual Graph of General Knowledge]]"
 for more information on knowledge graph construction in general.

These papers are an important addition to the literature for a deeper understanding of knowledge acquisition methodologies in the fields of machine learning and natural language processing.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
- I'd like to see you go so far as to acquire and summarize these references.
- Ah, so that's [[survey by Devin]].

---
This page is auto-translated from [/nishio/記号知識蒸留](https://scrapbox.io/nishio/記号知識蒸留) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.