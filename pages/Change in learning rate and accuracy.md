---
title: "Change in learning rate and accuracy"
---

- An experiment using MNIST to observe how learning progress changes when the learning rate is changed.
- As the epoch progresses, the error behaves as if it were going down and then slowly going up after reaching a minimum.
- The lower the learning rate, the smaller the minima.
- But the number of epochs required to get to the minima increases.
- When competing on the final accuracy (as is often the case with papers, etc.), it is advantageous to use a low learning rate and to put a large amount of computational resources into it.
- If computational cost is limited, it is better to repeat the learning process until a minimum is reached, even if it is accelerated by increasing the learning rate
![image](https://gyazo.com/b1a027d26df520115a3bf1c5e445146b/thumb/1000)
![image](https://gyazo.com/38a5af5201c6747a311ef59a97b82a24/thumb/1000)
---
This page is auto-translated from [/nishio/学習率と精度の変化](https://scrapbox.io/nishio/学習率と精度の変化) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.