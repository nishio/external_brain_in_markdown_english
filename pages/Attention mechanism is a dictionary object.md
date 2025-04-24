---
title: "Attention mechanism is a dictionary object"
---

- Is [[attention mechanism]] a [[dictionary object]]?

- Consider [internal volume caution
$Attention(query, Key, Value) = Softmax(query \cdot Key) \cdot Value$

- For vectors of higher dimensions, any two vectors have an inner product approximately equal to zero ([[Curse of the dimension]]).
- Using the [[soft-argmax]] approximation, it is practically argmax
- Even if a Key→Value function is difficult to acquire by learning, it can be created by memory
- The actual dictionary object determines key matches, but here the inner product proximity
    - Almost every inner product is zero, so space would be divided up fuzzy like this.
    - ![image](https://gyazo.com/4913eacee07f06b21aba1e8baa770671/thumb/1000)

[[Key-Value Memory Networks for Directly Reading Documents]]
- [https://arxiv.org/pdf/1606.03126.pdf](https://arxiv.org/pdf/1606.03126.pdf)

---
This page is auto-translated from [/nishio/注意機構は辞書オブジェクト](https://scrapbox.io/nishio/注意機構は辞書オブジェクト) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.