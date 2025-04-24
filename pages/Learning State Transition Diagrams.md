---
title: "Learning State Transition Diagrams"
---

How large a neural network is needed to learn a [[state change diagram]] of S-state N inputs?
Initially, I thought "two intermediate layers of O(S^2) size are needed," but I was able to learn with much smaller ones, so I explored the limits.
The input is a concatenation of S-dimensional one-hot and N-dimensional one-hot.
The output is one-hot in the new state S dimension.
The state transition table is randomly generated.
- In reality, there is more structure and compression is easier. Randomness is the most difficult problem.
- S * 1 S is determined for N inputs
The activation function is ReLU
Set EARLY_STOPPING=False, because if it is True, it will stop before the learning process starts.
The sizes of the intermediate layers were tried from the smallest to the largest, and the table shows the sizes that could correctly answer all of the S * N possible inputs.

Number of intermediate layers required for all patterns to be correct
| ↓S\N→ | 3 | 10 | 30 | 100 |
| -- | -- | -- | -- | -- |
| 3 | 4 | 8 | 8 | 8 |
| 6 | 8 | 8 | 16 | 24 |
| 10 | 8 | 16 | 24 | 36 |
| 13 | 8 | 16 | 32 | 60 |
| 16 | 8 | 8 | 36 | 60 |
| 20 | 8 | 8 | 32 | 90 |
| 40 | 16 | 28 | 60 | 135 |
| 60 | 16 | 28 | 90 | 135 |
Experiment (up to S=20): [https://gist.github.com/nishio/8d2dd6511df11c0aa78b542c7563b2a8](https://gist.github.com/nishio/8d2dd6511df11c0aa78b542c7563b2a8)
Additional experiments (S=40, 60): [https://gist.github.com/nishio/905160abc7766fcf239e6c7854465172](https://gist.github.com/nishio/905160abc7766fcf239e6c7854465172)

When I saw the results of this experiment, I thought, "What? Why is it OK to have such a small middle class? Isn't it buggy?" I thought,
To begin with, state transition diagrams can be realized without even an intermediate layer if the input is S*N one-hot. (Figure 2)
The question can be stated as "If we replace one-hot S*N with two-hot S+N by placing an intermediate layer, how many intermediate layer sizes are needed?
And this compresses more than you think. see [[Learning the identity map]]
![image](https://gyazo.com/d70cfab3fd55d1a5ea810e2f5c25eb15/thumb/1000)

So, it is possible to represent state transition diagrams with a multi-layer perceptron that is smaller and simpler than expected.

Associative: [[embedding a state into a vector space]].

---
This page is auto-translated from [/nishio/状態遷移図の学習](https://scrapbox.io/nishio/状態遷移図の学習) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.