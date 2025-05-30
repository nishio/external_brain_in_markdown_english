---
title: "Learning to Multiply"
---

- In [[Learning Addition]], we showed that learning addition with PositionalEncoding can be learned with an unexpectedly small neural network. This time, we will do multiplication of raw values.

There is a variable that takes two 0-1 values. The values of these variables are the inputs and the product is the output.
The training data, 10000 cases, will be generated in advance and commonly used in the following experiments.
The activation function is [[ReLU]]. Learning is up to 1 million epochs, [[EARLY STOPPING]].
The evaluation is based on the R2 coefficient of determination.

The size of the intermediate layer is changed to 2, 4, 8, and 16, and each is trained 10 times.
- To observe how the learning results change depending on the initial values of the weights of the neural net.
The following displays "{size}: {mean}+-{2 standard deviations}: {results for each of the 10 times}": {size}: {mean}+-{2 standard deviations}: {results for each of the 10 times}.

:

```
2: 0.777+-0.521: 0.854 0.853 0.854 0.853 0.854 -0.000 0.943 0.853 0.853 0.853
4: 0.908+-0.109: 0.957 0.854 0.959 0.959 0.854 0.854 0.853 0.979 0.958 0.853
8: 0.982+-0.030: 0.959 0.984 0.959 0.990 0.992 0.994 0.994 0.994 0.993 0.959
16: 0.992+-0.022: 0.998 0.995 0.960 0.996 0.995 0.997 0.996 0.996 0.994 0.997
```


Even with 8 intermediate layers, there are several training results with scores above 0.99.
In other words, 8 neural nets are sufficient in terms of their expressive capacity,
It has not been reached by random initial pulls.
The probability of reaching it has increased by increasing the number of intermediate layers.

For ReLU, the addition of real values is self-explanatory.

---
This page is auto-translated from [/nishio/掛け算の学習](https://scrapbox.io/nishio/掛け算の学習) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.