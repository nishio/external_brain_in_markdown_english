---
title: "log-bilinear model"
---

- log-bilinear language model
    - The probability of occurrence of the following words under a given context c is
    - $P(w|c) = \frac{\exp (\phi(w)\cdot c)}{\sum_{w'\in V} \exp (\phi(w)\cdot c)}$
    - The language model is that $\phi$ is an embedding function for the appropriate word
    - In short, take [[inner product]] and [[softmax]].
        - In A. Mnih and G. Hinton (2007), a little more advanced than mere inner product
        - ![image](https://gyazo.com/4b42aec31043b4fdfd07d353c4ee54ff/thumb/1000)
        - ![image](https://gyazo.com/12be19af95d085079f65326e8896b110/thumb/1000)

- Similarly, softmaxing after taking the inner product is [[internal volume caution]] (2015).

- Logarithmic [[bilinear]] model
- [[log bilinear model]]
- [[bilinear]]

- Log Bilinear Language Model
    - [[Mnih & Hinton, 2007]]
    - A. Mnih and G. Hinton (2007)
    - "Three new graphical models for statistical language modelling",
    - ICML, pp. 641–648, [http://www.cs.utoronto.ca/~hinton/absps/threenew.pdf](http://www.cs.utoronto.ca/~hinton/absps/threenew.pdf)

    - A. Mnih, Y. Zhang, and G. Hinton (2009)
    - "Improving a statistical language model through non-linear prediction",
    - Neurocomputing, vol. 72, no. 7-9, pp. 1414 – 1418
    - [http://www.sciencedirect.com/science/article/pii/S0925231209000083](http://www.sciencedirect.com/science/article/pii/S0925231209000083)

---
This page is auto-translated from [/nishio/対数双線形モデル](https://scrapbox.io/nishio/対数双線形モデル) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.