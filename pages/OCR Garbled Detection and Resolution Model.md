---
title: "OCR Garbled Detection and Resolution Model"
---

![image](https://gyazo.com/9a0519d3b62a4ff65d87609073152440/thumb/1000)

- [[OCR error]] detection and resolution model
- 1: Model to detect OCR corruption
    - There is a clear difference in the probability distribution of character occurrence between the OCR garbled area and the non-OCR garbled area.
    - Could be identified by a character-based CNN or Transformer.
- 2: Model to repair OCR corruption
    - The affiliate lengths are different, and it must be difficult to...
    - Put the garbled part and its surrounding context into a Transformer or other device that can take variable-length input as a set.
    - The decoder then spits out an indefinite-length output.
    - It seems that a human being would have to carefully create training data to learn...
    - Inverse functions are learned by feeding text with known correct answers to OCR

- Patterns of OCR Failure
    - Simply replaced by similar characters.
        - grass and trees to leathery trees
        - Web → Web
        - Blog → Prog
    - Horizontal text in vertical books is destroyed.
        - Office→0B8
    - Replaced by jumbled Chinese characters


---
This page is auto-translated from [/nishio/OCR化け検出解消モデル](https://scrapbox.io/nishio/OCR化け検出解消モデル) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.