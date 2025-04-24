---
title: "Vectorization of states"
---

- A [[condition]] is often thought of as an element ([[symbol]]) of a set of [[discrete]].
Consider extending this to [[vector space]].

In that case the transition probability is a function of the vector to vector probability distribution
- very
- Represented by several representative points in k-means fashion

Note on synthesis method
- superscription
    - $v \leftarrow v_{new}$
- conversion
    - $v \leftarrow A v_{now}$
- synthetic
    - $v \leftarrow v_{new} + A v_{now}$
    - Override when A=0
    - When vnew=0, conversion

I want the matrices and state vectors to be acquired by learning.
- Press the "Weird" button when you get a weird reaction.
    - Move to the second nearest representative point
    - Make negative examples training data.
    - (2019 addendum)
        - The idea is to keep representative points even after the state is embedded in the vector space
        - A representative point is just "a set of things that humans were able to verbalize in the first stage, saying, 'This is the kind of state of affairs that exists.
        - When discretizing after vectorization, one could [[Voronoi division]] at the first representative point, or one could [[k-means]] on the new distribution.
- Positive response
    - Is direct action the only positive example?
    - Elicit that action as soon as possible.
        - [[reinforcement learning]]

---
This page is auto-translated from [/nishio/状態のベクトル化](https://scrapbox.io/nishio/状態のベクトル化) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.