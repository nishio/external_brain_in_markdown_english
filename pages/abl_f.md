---
title: "abl_f"
---

[F - Heights and Pairs](https://atcoder.jp/contests/abl/tasks/abl_f)
- ![image](https://gyazo.com/a6ccf80048638b04d410f8a8df2b7275/thumb/1000)
- Thoughts.
    - [[superfluous event]] for "none of the pairs are the same height"
    - It is a combination of "one pair of..." and "two pairs of..."
        - [[principle of inclusion]]
    - I guess I'd make a [[frequency table]] of heights first.
    - The way the pair is taken is the target, so the state can be compressed.
    - How many "combinations with one pair" are there when there are two, three, four, and so on pairs?
    - Maybe this is not an equation transformation, but a DP to get it?
    - The order is not relevant to how the pairs are taken, so you can introduce the order here
    - Maybe DP in the number of cases where j pairs are made with the first i of a given frequency table X.
    - If there are more than 4 people, there is a possibility of having 2 pairs at a time.
        - 4C2×2C2÷2!
    - N will be almost 100,000...
- No official commentary
- explanation
    - [https://betrue12.hateblo.jp/entry/2020/09/27/043205](https://betrue12.hateblo.jp/entry/2020/09/27/043205)
    - [https://tiramistercp.hatenablog.com/entry/abl-f](https://tiramistercp.hatenablog.com/entry/abl-f)
    - It's the principle of inclusion and exclusion." OK.
    - Create a frequency table" OK
    - Number of cases where k pairs are taken from a set of size 4 or larger" OK
    - Is it DP?" No, it's [[convolution]].
        - When doing [[repetitive fold]], you need to be creative with the order.
        - Attach the shortest first.

---
This page is auto-translated from [/nishio/abl_f](https://scrapbox.io/nishio/abl_f) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.