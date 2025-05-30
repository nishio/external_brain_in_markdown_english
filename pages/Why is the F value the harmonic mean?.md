---
title: "Why is the F value the harmonic mean?"
---

from  [[F value]]
Why is the F value the harmonic mean?

What is F value [http://scikit-learn.org/stable/modules/generated/sklearn.metrics.f1_score.html](http://scikit-learn.org/stable/modules/generated/sklearn.metrics.f1_score.html)
- `F1 = 2 * (precision * recall) / (precision + recall)`
- Max 1 Min 0
- When precision == recall, F value is the same value
- When either precision or recall is 0, F1 is also 0.
![image](https://gyazo.com/5645c89ab5b98065c1903cee82c3c507/thumb/1000)

- TP: True Positive
- FP: False Positive
- FN: False Negative
- TN: True Negative
- Precision:
- $P = \frac{TP}{TP+FP}$
- Recall:
- $R=\frac{TP}{TP+FN}$
- Sum of reciprocals
- $\frac{1}{P} + \frac{1}{R} = \frac{2TP+FP+FN}{TP}$
- F1 score is the harmonic mean of P and R
- $F1 = \frac{2 P R}{P + R} = \frac{2 \frac{TP}{TP + FP} \frac{TP}{TP + FN} }{\frac{TP}{TP + FP} +\frac{TP}{TP + FN}} = \frac{2 TP}{(TP + FN) + (TP + FP)} = \frac{2 TP}{2TP + FN+ FP}$
- $\frac{2}{\frac{1}{P} + \frac{1}{R}} = \frac{2TP}{2TP + FP + FN}$
- Normalized Symmetric Difference [http://www.dcs.gla.ac.uk/Keith/pdf/Chapter7.pdf](http://www.dcs.gla.ac.uk/Keith/pdf/Chapter7.pdf) p.128
- $E = \frac{FP + FN}{2TP + FP + FN}$
- F1 and E add 1: F1 + E = 1

- Fβ Score
- $F_\beta = \frac{(1 + \beta ^ 2) TP}{(1 + \beta^2) TP + \beta^2 FN + FP}$
- $\frac{1}{P} + \frac{\beta^2}{R} = \frac{(TP+FP)+\beta^2(TP+FN)}{TP}$
- In short, Recall with $\beta^2$ weighted harmonic mean
- Why $\beta^2$ instead of $\beta$?
- $F_\beta = \frac{(1 + \beta ^ 2) TP}{(1 + \beta^2) TP + \beta^2 FN + FP} = \frac{1+\beta^2}{\frac{1}{P} + \frac{\beta^2}{R}}$
- The coefficients are omitted and written as Z
- $\frac{\partial F_\beta}{\partial R} = Z \frac{\beta^2}{R^2}, \frac{\partial F_\beta}{\partial P} = Z \frac{1}{P^2}$
- That is, the gradients match when [$ \beta P = R
- The fact that the gradients match means that "the effect on the score is the same when P and R are moved by the same amount.
- Does it mean that equilibrium is reached when R is β times greater than P?
---
This page is auto-translated from [/nishio/F値はなぜ調和平均なのか](https://scrapbox.io/nishio/F値はなぜ調和平均なのか) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.