---
title: "Feature Matching for Text Generation"
---

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>What is Feature Matching?
- [[Salimans+ 2016]]
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>What is Maximum Mean Discrepancy?

Use [[LSTM]] for G in [[GAN]] and [[TextCNN]] for D and E
- What's E? →Encoder

### Soft-argmax approximation
- There is some difficulty in handling argmax because it is not differentiable, but I suggest that this could be replaced with softmax.
- $W[\arg\max_i x_i] \approx W \mathrm{softmax}(L x_i)$
- where L is a large scalar, such as 1000, which coincides with argmax in the limit L → ∞.
- The stability of the calculation may need to be taken care of separately. Related [[logsumexp]].
- [[Soft-argmax]]

[Adversarial Feature Matching for Text Generation | DL Hacks](https://hacks.deeplearning.jp/adversarial-feature-matching-for-text-generation/)
[DL Roundtable Adversarial Feature Matching for Text Generation [https://www.slideshare.net/DeepLearningJP2016/dladversarial-feature-matching-for-](https://www.slideshare.net/DeepLearningJP2016/dladversarial-feature-matching-for-) text-generation]

---
This page is auto-translated from [/nishio/Feature Matching for Text Generation](https://scrapbox.io/nishio/Feature Matching for Text Generation) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.