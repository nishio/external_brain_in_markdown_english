---
title: "Derivation of Fisher matrix from KL distance"
---


- Definition of [[Kullback-Leibler divergence]]([[KL Distance]]): The
- $D(P, Q) = \int_\Omega P(\omega)\log{P(\omega) \over Q(\omega)} d \omega$
- When symmetrized:.
- $D'(P, Q) \equiv D(p, Q) + D(Q, P)$
- $= \int_\Omega P(\omega)\log{P(\omega) \over Q(\omega)} + Q(\omega)\log{Q(\omega) \over P(\omega)} d \omega$
- $= \int_\Omega (P(\omega) - Q(\omega))\log{P(\omega) \over Q(\omega)} d \omega$

- KL distance of the probability distribution of a parameter θ and a parameter slightly (δ)-displaced:.
- $D'(P(\omega| \theta+\delta), P(\omega|\theta)$
- $= \int_\Omega (P(\omega| \theta+\delta) - P(\omega| \theta))\log{P(\omega| \theta+\delta) \over P(\omega| \theta)} d \omega$
- Now put $\Delta \equiv P(\omega| \theta+\delta) - P(\omega| \theta)$.
- $= \int_\Omega \Delta \log{P(\omega| \theta) + \Delta  \over P(\omega| \theta)} d \omega$
- $= \int_\Omega \Delta \log \left( 1 + {\Delta  \over P(\omega| \theta)} \right) d \omega$
- By [[Taylor expansion]] of the logarithm and a first-order approximation
- $\log(1 + x) \approx x$
- therefore
    - $\int_\Omega \Delta \log \left( 1 + {\Delta  \over P(\omega| \theta)} \right) d \omega \approx \int_\Omega { \Delta^2  \over P(\omega| \theta)}  d \omega$

- First-order approximation of the difference in function values:.
- $f(x+dx)-f(x) \approx f'(x)dx$
- due to
- $\Delta \equiv P(\omega| \theta+\delta) - P(\omega| \theta) \approx \sum_i {\partial P(\omega | \theta) \over \partial \theta_i} \delta_i$
- By the derivative of the logarithm [$ (\log x)' = x' / x
- $= P(\omega|\theta) \sum_i {\partial \log P(\omega | \theta) \over \partial \theta_i} \delta_i$
- Substituting Δ:.
    - $\int_\Omega { \Delta^2  \over P(\omega| \theta)}  d \omega   \approx   \int_\Omega \left( \sum_i {\partial \log P(\omega | \theta) \over \partial \theta_i} \delta_i \right)^2 P(\omega | \theta) d\omega$

To organize:.
- $\int_\Omega \left( \sum_i {\partial \log P(\omega | \theta) \over \partial \theta_i} \delta_i \right)^2 P(\omega | \theta) d\omega$
- $= {\mathbb E} \left[  \left( \sum_i {\partial \log P(\omega | \theta) \over \partial \theta_i} \delta_i \right)^2 \right]$
- $= \sum_i \sum_j {\mathbb E}\left[ {\partial \log P(\omega | \theta) \over \partial \theta_i} {\partial \log P(\omega | \theta) \over \partial \theta_j} \right]_{ij} \delta_i\delta_j$
- $= \sum_i \sum_j \mathcal{F}(\theta)_{ij} \delta_i \delta_j$

- To summarize so far
    - $D'(P(\omega| \theta+\delta), P(\omega|\theta) \approx \sum_i \sum_j \mathcal{F}(\theta)_{ij} \delta_i \delta_j$
- That is, the [[metric tensor (physics)]] of the space containing the KL distance is the [[Fisher matrix]] (

---
This page is auto-translated from [/nishio/KL距離からのFisher行列の導出](https://scrapbox.io/nishio/KL距離からのFisher行列の導出) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.