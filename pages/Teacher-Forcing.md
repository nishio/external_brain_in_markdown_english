---
title: "Teacher-Forcing"
---

![image](https://gyazo.com/ae986c8c66b27fc57b06cf8991917f64/thumb/1000)

A learning method that uses the correct data instead of using the output of the previous self as input.
It solves the problem of slow learning due to the accumulation of errors in the later stages of the training process, but it also has the problem of not supplying the correct data one character at a time when it is actually used.
Use [[Scheduled Sampling]] to randomly select your output and the correct answer: [[Samy Bengio+ 2015]].

---
This page is auto-translated from [/nishio/Teacher-Forcing](https://scrapbox.io/nishio/Teacher-Forcing) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.