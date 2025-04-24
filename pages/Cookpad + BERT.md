---
title: "Cookpad + BERT"
---

Cookpad's experience with self-training [[BERT]] with in-house data.
[BERT with SentencePiece to learn Japanese-specific pre-trained models and solve tasks based on them - Cookpad Developer Blog](https://techlife.cookpad.com/entry/2018/12/04/093000)

- > BERT's multilingual model is not suitable for handling Japanese, so use [[SentencePiece]].
    - Related [[Why Google Bert's tokenizer can get muddled sounds?]]
- >  Use Cookpad cooking instructions text (approx. 16 million sentences) for pre-training
- >  Learning takes about 3.5 days on a p3.2xlarge instance
    - p3.2xlarge is 3USD/hour, so about 25,000.

---
This page is auto-translated from [/nishio/クックパッド+BERT](https://scrapbox.io/nishio/クックパッド+BERT) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.