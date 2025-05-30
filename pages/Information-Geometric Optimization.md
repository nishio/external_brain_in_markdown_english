---
title: "Information-Geometric Optimization"
---

2019-07-29
When converting an objective function defined in the search space to a function defined in the parameter space, the method of taking the expectation value was generally used in the past, but since [[the mean is not an invariant to the mapping of the objective function by a monotonically increasing function]], it was changed to a definition using quantiles.
- Workshop Presentation: [[Introduction to Information-Geometric Optimization]].

![image](https://gyazo.com/0a5fbd0a8c79402a155318bd154447b5/thumb/1000)

[http://www.jmlr.org/papers/volume18/14-467/14-467.pdf](http://www.jmlr.org/papers/volume18/14-467/14-467.pdf)
- We present a canonical way to turn any smooth parametric family of probability distributions on an arbitrary search space 𝑋 into a continuous-time black-box optimization method on 𝑋, the [[information-geometric optimization]] ([[IGO]]) method.
- [[Invariance]] as a major design principle keeps the number of arbitrary choices to a minimum.
- The resulting [[IGO flow]] is the flow of an ordinary differential equation conducting the [[natural gradient ascent]] of an adaptive, time-dependent transformation of the objective function.
- It makes no particular assumptions on the objective function to be optimized.
- The IGO method produces explicit [[IGO algorithms]] through time discretization.
- It naturally recovers versions of known algorithms and offers a systematic way to derive new ones.
    - In continuous search spaces, IGO algorithms take a form related to [[natural evolution strategies]] ([[NES]]).
    - The [[cross-entropy method]] is recovered in a particular case with a large time step, and can be extended into a smoothed, parametrization-independent maximum likelihood update (IGO-ML).
    - When applied to the family of Gaussian distributions on $R^d$, the IGO framework recovers a version of the well-known [[CMA-ES]] algorithm and of [[xNES]].
    - For the family of [[Bernoulli distributions]] on $\{0, 1\}^d$, we recover the [[seminal PBIL]] algorithm and [[cGA]].
    - For the distributions of restricted Boltzmann machines, we naturally obtain a novel algorithm for discrete optimization on $\{0, 1\}^d$.
- All these algorithms are natural instances of, and unified under, the single information-geometric optimization framework.
- The IGO method achieves, thanks to its intrinsic formulation, maximal invariance properties:
    - invariance under reparametrization of the search space 𝑋,
    - under a change of parameters of the probability distribution,
    - and under increasing transformation of the function to be optimized.
    - The latter is achieved through an adaptive, quantile-based formulation of the objective.
- Theoretical considerations strongly suggest that IGO algorithms are essentially characterized by a minimal change of the distribution over time. Therefore they have minimal loss in diversity through the course of optimization, provided the initial diversity is high. First experiments using restricted Boltzmann machines confirm this insight. As a simple consequence, IGO seems to provide, from information theory, an elegant way to simultaneously explore several valleys of a fitness landscape in a single run.

- search space: X
    - Can be finite, discrete infinite, or continuous.
- objective function$f: X \to R$
- black-box senario: no knowledge about f other than finding f(x) is assumed
- invariance
    - extends performance observed on a single function to an entire associated invariance class
    - generalizes from a single problem to a class of problems
    - ??
    - Thus it hopefully provides better robustness w.r.t. changes in the presentation of a problem.
- For continuous search spaces, invariance under translation of the coordinate system is standard in optimization.
    - <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Ah, the concept of invariants.
- Invariance under general affine-linear changes of the coordinates has been
    - Nelder-Mead Downhill Simplex method (Nelder and Mead, 1965),
    - quasi-Newton methods (Deuflhard, 2011)
    - [[covariance matrix adaptation evolution strategy]], [[CMA-ES]] (Hansen and Ostermeier, 2001; Hansen and Auger, 2014)
- These are invariants to the search space
- On the other hand, monotonically increasing transformations for the objective function

- iteratively update a probability distribution $𝑃_\theta$ defined on 𝑋, parametrized by a set of parameters $\theta$
    - This probability distribution can be said to be a [[belief]] about the solution (in the sense of [[POMDP]], etc.).

- [[estimation of distribution algorithms]] ([[EDA]])
    - Method 1: The cross-entropy method consists in taking 𝜃 minimizing the Kullback-Leibler divergence between 𝑃𝜃 and the indicator of the best points according to 𝑓
        - What is indicator of the best points according to f?
    - Method 2: one can transfer the objective function 𝑓 to the space of parameters 𝜃 by taking the average of 𝑓 under 𝑃𝜃, seen as a function of 𝜃.
        - This average is a new function from an Euclidian space to R and is minimal when 𝑃𝜃 is concentrated on minima of 𝑓.
            - Is it assumed that theta is one dimensional?
            - If not, you can still solve it using the gradient method.
    - Amari's Natural Gradient Method.
        - More efficient than ordinary gradients
- Euler time discretization
    - Euler method
    - In front of Lungekutta

- Maybe the place with (1) is off by one.

- 2.2.1
    - To make f a function over theta instead of X, you can take the expected value in theta.
    - but
        - Expectations are susceptible to extreme values.
        - Not invariant to monotonically increasing transformations
    - So use hundredths.
        - The median is the median even if it's transformed by a monotonically increasing function.

---
This page is auto-translated from [/nishio/Information-Geometric Optimization](https://scrapbox.io/nishio/Information-Geometric Optimization) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.