---
title: "dual segment tree"
---

[On the notion of a dual segment tree - The Rabbit Hutch](https://kimiyuki.net/blog/2019/02/22/dual-segment-tree/)
[Dual Segment Tree / Lazy Segment Tree Halving Technique - HackMD](https://hackmd.io/@tatyam-prime/DualSegmentTree)
- What I thought was a dual segment tree, is probably a half delayed segment tree.
        - [[Propagation down the dual segment tree]]
        - > The implementation unintentionally assumed that the action was commutative.
        - > Incorrect operation for non-replaceable "overwrite action
        - > Timestamping turned it into a commutative max operation.
    - This would correspond to the following
        - > Two Two-Segment Segment Trees
        - > When the action does not change the result even if the order of actions is changed, such as interval add and interval chmin, the action side can be processed like a normal segment tree, which is slightly faster.
        - > How to do interval assignment
        - > (time, value to be assigned) can be paired and chmaxed.

---
This page is auto-translated from [/nishio/双対セグメント木](https://scrapbox.io/nishio/双対セグメント木) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.