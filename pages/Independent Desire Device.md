---
title: "Independent Desire Device"
---


![image](https://gyazo.com/2c9ec54a8c63cc77b23703d197bf890e/thumb/1000)


- In a [[hostile generative network]] ([[GAN]]), a generative network outputs forgeries and a discriminative network identifies the authenticity of that output.
At this time, the generating network performs [[imitation]].

![image](https://gyazo.com/9142a7a137f72cded52940ea48a193f2/thumb/1000)
If this generative network has sufficient expressive power, it can perfectly mimic the original given as training data. At this time, the discriminative network will not be able to identify it.
So we expect to learn a "reasonable balance" by making the loss function common and optimizing it at the same time.

Learn enough about this and then add "[[desire for independence]] network".

![image](https://gyazo.com/2c9ec54a8c63cc77b23703d197bf890e/thumb/1000)

It determines how far the output of the generative network is "from what is given as a sample". The farther away, the better the score.
However, at the same time, the discriminative network determines whether the output is within the subspace represented by the given sample, so if the output is too far away from the sample, the score of the discriminative network will decrease.
This produces "something that does not resemble the sample data, but is in the space represented by the sample data.

- [[desire for independence]]

---
This page is auto-translated from [/nishio/独立欲求装置](https://scrapbox.io/nishio/独立欲求装置) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.