---
title: "Adversarial Examples"
---

- How to make inputs misrecognize image classification by machine learning
- AEs in one model are easily misclassified in another model
    - In other words, it's a case study that doesn't appear very often in nature.

Transferability in Machine Learning: from Phenomena to Black-Box Attacks using Adversarial Samples
[https://arxiv.org/abs/1605.07277](https://arxiv.org/abs/1605.07277)
![image](https://gyazo.com/0cfa921d2c9d6a3306f04439d0edb48b/thumb/1000)
- How successful is the attack when the AE made on hand is fed to another model?
- LR is surprisingly strong.
    - Image of beating with a rustic blunt instrument
- Interesting that kNN is so strong.
    - Since the perturbation with a distance limit is used to fool a model that judges by distance, it is likely that the perturbation is generated to target a good point.

---
This page is auto-translated from [/nishio/Adversarial Examples](https://scrapbox.io/nishio/Adversarial Examples) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.