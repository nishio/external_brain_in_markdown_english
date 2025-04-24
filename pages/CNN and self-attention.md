---
title: "CNN and self-attention"
---

- CNN], which could only accept fixed-length input, has been replaced by [[attention mechanism]], which can accept indefinite-length input.
- Why can we extend to indefinite length?
- The CNN was hard-coded in the form of a matrix to determine which position values were multiplied by what weight, relative to itself
    - So it was necessary to fix in advance how many values to process before and after ![image](https://gyazo.com/adfdef7c11d9c8c05bb40d3be79eefbd/thumb/1000).

- The attention mechanism determines what weights to multiply by the value of the
    - So there's no need to predetermine the number of pieces.
    - ![image](https://gyazo.com/1902ffd4c16d50ff825b1b2573fdc97e/thumb/1000)

    - Instead, the value returned by the attention mechanism is the same even if the input columns are shuffled because there is no position information in the simple configuration

- [[Transformer]] combines [Positional Encoding
    - Embed location information in the input value itself.
    - Now the attention mechanism can take the place of CNN.

---
This page is auto-translated from [/nishio/CNNと自己注意](https://scrapbox.io/nishio/CNNと自己注意) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.