---
title: "COMET: Commonsense Transformers for Automatic Knowledge Graph Construction"
---

![image](https://gyazo.com/fb0e9ead12ab12f78ec1c4b720576632/thumb/1000)
[https://arxiv.org/abs/1906.05317](https://arxiv.org/abs/1906.05317)

<img src='https://scrapbox.io/api/pages/nishio-en/o3-mini-high/icon' alt='o3-mini-high.icon' height="19.5"/>
- Purpose and background.
- COMET is a method for automatically generating "missing parts" of common knowledge graphs such as [[ATOMIC]] and [[ConceptNet]]. It is unique in that it makes tacit common knowledge explicit in a language-generating model, whereas conventional knowledge extraction relies on explicit descriptions.

- METHOD.
    - It is pre-initialized with the weights of a large-scale language model (GPT) and fine-tuned using existing knowledge tuples (subject, relation, and object).
    - A new knowledge tuple is constructed by giving a subject and a relation as input and generating an object.
    - Utilizes the Transformer architecture's multi-head attention and feed-forward layers to effectively capture contextual information.

- Experimental results.
    - In human evaluation, accuracy was confirmed at 77.5% for ATOMIC and 91.7% for ConceptNet, demonstrating near-human performance.
    - It was also shown that much of the knowledge generated was novel and not contained in the existing training data.
    - The use of pre-trained models has yielded significant performance gains compared to random initialization.

- Significance
- Expanding the common sense knowledge base through automatic generation is a promising approach to replace conventional extraction-based methods, and is expected to be applied to a wide range of knowledge base construction in the future.

The above is an overview of COMET and its main contributions.
---
This page is auto-translated from [/nishio/COMET: Commonsense Transformers for Automatic Knowledge Graph Construction](https://scrapbox.io/nishio/COMET: Commonsense Transformers for Automatic Knowledge Graph Construction) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.