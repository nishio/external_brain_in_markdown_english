---
title: "principle of inclusion"
---

When the number of cases of an event is difficult to count directly, it is solved by dividing it into smaller and simpler counts [[problem partitioning]]. When the partial events are exclusive, they simply add up, but even if they do not, the inclusion-division principle can be used if the common part can be found.

$| A \cup B | = |A| + |B| - |A \cap B|$
- [https://ja.wikipedia.org/wiki/包除原理](https://ja.wikipedia.org/wiki/包除原理)

- [[binary feature]].


![image](https://gyazo.com/afe3d4832a4c5543a2d318ddc95e32d7/thumb/1000)
- When you want to find 000 but it is difficult to find it directly, calculate *** - (1** + *1* + **1) + (11* + 1*1 + *11) - (111)
- In particular, if the size f(k) of the set is determined by the number k of 1s
    - $\sum_k -1^k \binom{n}{k} f(k)$
- [https://twitter.com/opt_cp/status/1298569230439157762](https://twitter.com/opt_cp/status/1298569230439157762)
- $| \bigcap_{i \in V}A_i | = \sum_{S \subseteq V} (-1)^{|S|} | \bigcap_{i\in S} A_i^{\mathsf c} |$
- >  Instead of thinking |A or B| = |A| + |B| - |A and B|, it is easier to think |¬A and ¬B| = |U| - |A| - |B| + |A and B| [src [https://twitter.com/Euglenese/status/1277087618606329856?s=](https://twitter.com/Euglenese/status/1277087618606329856?s=) 20] [[ABC172E]]
    - $| A \cup B | = |A| + |B| - |A \cap B|$
    - $| A^{\mathsf c} \cap B^{\mathsf c} | = |U| - |A| - |B| + |A \cap B|$
- > Name the events properly and transform the equation; be aware of which events can be easily calculated.
    - > Consider the case where N=3 this time. Let #() denote the number of elements in the event.
    - >  Pi = (the event that Ai=Bi), we want to find #(¬P1 ∧ ¬P2 ∧ ¬P3), and #(P1) or #(P1 ∧ P2) can be easily computed. #(¬P1 ∧ ¬P2) is not so easy to deal with, so it is easy to use de Morgan to convert it to #(¬(P1 ∨ P2 ∨ P3)) and think of it as the inclusive divisor principle.
    - [https://twitter.com/oinori1197/status/1276894798209679360](https://twitter.com/oinori1197/status/1276894798209679360)

- [[The Inclusion-Decomposition Principle Expand the range of solvable counts.]]  tsutaj
- [https://compro.tsutaj.com//archive/181015_incexc.pdf](https://compro.tsutaj.com//archive/181015_incexc.pdf)
- If small, full search
- Symmetry results in combination
    - O(2^N) becomes O(N)
- O(3^N) when using the inclusion principle for each subset
    - Why? → [[Sum of the number of subsets of a subset]].
    - This is a heavy I
        - [[fast Möbius transformation]] can make this O(N2^N)

relevance
    - [[binomial coefficient]]
    - [[Moebius transform]]
    - [[perfect permutation]]
- [https://twitter.com/sugarknri/status/1290212350696415233](https://twitter.com/sugarknri/status/1290212350696415233)
    - [[Euler's constant]]  [https://twitter.com/kaitou_ryaku/status/1239816691523051520](https://twitter.com/kaitou_ryaku/status/1239816691523051520)

---
This page is auto-translated from [/nishio/包除原理](https://scrapbox.io/nishio/包除原理) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.