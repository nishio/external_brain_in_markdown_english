---
title: "Positional Encoding"
---

[[Transformer]]
![image](https://gyazo.com/1bc1a16a113f46091aacb7f3fdcb92cd/thumb/1000)
[https://arxiv.org/pdf/1706.03762.pdf](https://arxiv.org/pdf/1706.03762.pdf)

In short, i rotating unit vectors, each with a rotation period of
- Rotation period$2\pi$: [$ \sin(pos), \cos(pos)
- Rotation period $10000 \cdot 2\pi$: $\sin(pos / 10000), \cos(pos / 10000)$
is equi-proportionately chopped between the

- The concept of [[position]] is often taken in the [[real number line]] sense, but it is expressed as a value that [[cycles]] through the position. Therefore, if there is an infinitely long series, "the same position" will always repeat itself, but if the cycle is long enough, there is no practical problem. Even the earth's surface is actually in a cycle, but in everyday life we think of it as a Cartesian coordinate system.
- #Rotational encoding

It adds them together rather than concatenating them against the input, but that seems to be OK.

---
This page is auto-translated from [/nishio/Positional Encoding](https://scrapbox.io/nishio/Positional Encoding) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
positional encoding
- Representation of position by mixing a rotating unit vector as position information
    - Unlike CNN, the attention mechanism does not have position information, so it cannot realize "what is the previous word" by itself, but when the word is changed to [[embedded vector]], the position information of the word is also embedded, so the attention mechanism can make position-based decisions. So the attention mechanism can make judgments based on position.
    - It is also clever that this position is represented by a rotating unit vector, so that the relation "n words before" can be easily expressed by matrix multiplication when encoded in this way, and how much ambiguity is allowed can be expressed by inserting a number of different rotation cycles.
    - This combination of [[positional encoding]] and [[self-caution]] is supposed to be great!

---
This page is auto-translated from [/nishio/位置エンコーディング](https://scrapbox.io/nishio/位置エンコーディング) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.