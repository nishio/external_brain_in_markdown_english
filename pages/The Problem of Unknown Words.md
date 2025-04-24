---
title: "The Problem of Unknown Words"
---

2018-10-14
- I was trying to learn a NN that discriminates between X and not X.
- If you create a vocab from X, and then set [[unknown language]] to a word that does not appear in that vocab of not X, you have the obvious loophole of "if an unknown word appears, then not X".
- Should we synthesize both vocabularies?
    - union, wouldn't it end up being a quicker way to learn "NOT X when this word comes up"?
    - Shall we intersect?

:

```
>>> len(vocab)
37578
>>> len(c.keys())
4891
>>> len(set(c.keys()).intersection(vocab))
3592
```


- Wouldn't a large part of X's vocabulary be lost?
- Is that what you want?
- not Calculate the frequency of UNKs in X and then remove them from the X vocab so that they are UNKs with the same frequency?
:

```
>>> sum(c.values())
354748
>>> sum(c[k] for k in c if k not in vocab)
16071
>>> 16071 / 354748
0.045302580987066875
```


:

```
>>> z = np.load("words.npz")
>>> count = z["count"][:,1].astype(int)
>>> count.sum()
1633886
>>> _ * 0.0453
74015.0358
>>> count[count < 10].sum()
73467
>>> count[count <= 10].sum()
77827
```


If you UNK the words that only appear 10 times or less, the ratio is roughly the same.
That seems about right.

---
This page is auto-translated from [/nishio/未知語の問題](https://scrapbox.io/nishio/未知語の問題) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.