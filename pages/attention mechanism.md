---
title: "attention mechanism"
---

- [[attention (heed)]] ([[Attention]])
Generalization as of 2018
- $\mathrm{Attention}(query, Keys, Values) = \mathrm{Normalize}(F(query, Keys)) \cdot Values$
- There are queries and Keys, which are a bunch of multiple keys.
- There is a function F that takes a query and Keys as arguments and returns the intensity of attention for each key.
- The results are then normalized in some way to sum to 1 to obtain the attention intensity (roughly softmax, see [[Hard attention mechanism]]).
- Weighted average Values by their attention intensity

- schematic
    - ![image](https://gyazo.com/211618e709ff284a379c5c2f502934da/thumb/1000)

- F does not know the number of Key. $F(query, Key)$ does not depend on the shape of Key.
    - I don't know how to express this in mathematical terms.
    - There is a function f that takes one query and one key, and `[f(query, key) for key in Keys]`.

2014 [[view of addition]] [1409.0473 Neural Machine Translation by Jointly Learning to Align and Translate](https://arxiv.org/abs/1409.0473)
- Func := Feed-Forward Network
- $Attention(query, Key, Value) = Softmax(FFN(concat(query, Key))) \cdot Value$
- > By letting the decoder have an attention mechanism, we relieve the encoder from the burden of having to encode all information in the source sentence into a fixedlength vector. With this new approach the information can be spread throughout the sequence of annotations, which can be selectively retrieved by the decoder accordingly.
- The hidden state of the RNN is a fixed-length vector, and it is a burden to remember to pack the entire sentence's data into it
- Attention mechanism can retrieve information from data of arbitrary length, thus reducing its burden
    - ![image](https://gyazo.com/dab69f04c581681e9c3c543b92633ef5/thumb/1000)


2015 [[internal volume caution]] [1508.04025 Effective Approaches to Attention-based Neural Machine Translation [https://arxiv.org/abs/1508.](https://arxiv.org/abs/1508.) 04025]
- Split that query and key are simply inner products of query and key
- $Attention(query, Key, Value) = Softmax(query \cdot Key) \cdot Value$
- Of course, this inner product is sometimes expressed as a matrix product in some papers.
- Related [[bilinear]].
![image](https://gyazo.com/1db88d9a61dcce7af368f0d0e594b3f1/thumb/1000)

- [[Source Target Attention]] and [[self-caution]] ([2017](https://arxiv.org/abs/1703.03130))
- Initially, the attention mechanism was envisioned to be used in combination with RNNs
- Store the Encoder's hidden states in the Encoder-Decoder configuration and select from among those hidden states by the attention mechanism
- In this configuration, Key and Value come from Encoder and query comes from Decoder.
- This type of configuration is called [Source Target Attention
    - ([Sequence Generation with Target Attention](http://ecmlpkdd2017.ijs.si/papers/paperID307.pdf) (2017) for a comparative discussion in the form of source-target attention and target- target attention in the form of comparative discussion.)
- K and V together are called Memory
- Synonyms are [[self-caution]] (Self-attention)
    - This one is Key, Value, query all are self... no, that definition is not balanced by the level of abstraction...
    - It may eventually differentiate into better terms.
    - So far, one implementation example is "everything comes from the lower layers."
        - In this form, it's a development of [[CNN]].
        - CNNs that could only accept fixed-length input were replaced by [[attention mechanism]] that could accept indefinite-length input.
        - Commentary on this replacement: [[CNN and self-attention]].


-----
Old commentary
- This commentary implicitly assumes [[RNN]] and is not generalized: it is not a generalization.
    - Save past [[hidden state]].
    - Create a scalar that represents the appropriate intensity of attention from "the current hiding state and its hidden states."
    - Normalize that scalar to a total of 1
    - Used for a weighted average of each hidden state
        - There is a way to use output layer values instead of past hidden states.
---
This page is auto-translated from [/nishio/注意機構](https://scrapbox.io/nishio/注意機構) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.