---
title: "embedding a state into a vector space"
---

    - [[Learning the identity map]]
    - It was found that one-hot vectors of arbitrary dimension can be embedded in 2-dimensional space in a form that is identifiable by the perceptron
- Discrete states can be represented by one-hot vectors
- This means,
- The state is considered a two-dimensional vector.

- I had a related thought a long time ago: [[Vectorization of states]].
    - At this time I was thinking of constructing a direct
    - Why did you want to state vectorize?
    - I wanted the state transitions to be acquired and improved through learning.

    - [[Learning State Transition Diagrams]]
    - This approach is to create training data from a given state transition diagram and train it with a multilayer perceptron.
    - I want to replace existing state transition diagrams written in hard code with neural nets.
    - This is the same concept as in [Replace conditional clauses in if statements with 2-class classification

- State usually [recurrent
    - If this recurrent part of the system does not need to be human observable, there is no need to make it discrete.
    - Then you can turn it in a compressed vector state.
    - ![image](https://gyazo.com/2c30201d8b958771518aacecd6940bd4/thumb/1000)


    - [[Reinforcement learning]] for [[continuous state]] may also be relevant

---
This page is auto-translated from [/nishio/状態のベクトル空間への埋め込み](https://scrapbox.io/nishio/状態のベクトル空間への埋め込み) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.