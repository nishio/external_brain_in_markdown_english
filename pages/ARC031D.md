---
title: "ARC031D"
---

[D - good shopper](https://atcoder.jp/contests/arc031/tasks/arc031_4)
![image](https://gyazo.com/50034b043205910e44c64d335da3c8bf/thumb/1000)

- Thoughts.
    - Known to be minimum cut entanglement
    - Buying an item or not is a choice between two options, so it makes the cut.
    - Can you solve a problem that maximizes a ratio with a minimum cut?
        - Bicubic search with ratio maximization as a decision problem?
            - [[Maximization with bisection search.]]
    - How would you describe the experience that is gained when multiple items are all purchased?
        - First, experience is a gain, so make it a "loss if you didn't buy one of several items".
        - ![image](https://gyazo.com/490dc64aefcb2601e8db7a000c9a1e36/thumb/1000)
    - If "not bought" is in the red, then the purchase cost is honestly on the side.
    - The experience side is the sum of all experience values E minus the actual experience value e $E - e$.
- Transforming the ratio equation, let e be the experience value and c the purchase cost.
    - $e/c > X$
    - $e > cX$
    - $e - cX > 0$
    - $cX - e < 0$
    - If the left side is negative when minimized, it means the ratio can be greater than X.
    - $cX + E - e < E$
    - That is, the cost side is multiplied by X. If the cost of the cut is less than E when the minimum cut is obtained, the ratio can be greater than X.


---
This page is auto-translated from [/nishio/ARC031D](https://scrapbox.io/nishio/ARC031D) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.