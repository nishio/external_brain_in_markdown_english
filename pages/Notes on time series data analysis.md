---
title: "Notes on time series data analysis"
---

[A list of points to keep in mind when analyzing time-series data, which is common in the field of practice - Blog of a data scientist working in Roppongi](http://tjo.hatenablog.com/entry/2017/09/22/190000)
- There is a [[correlation]] between the two [[time series data]], but only the weekly periodic component is on both, and if you remove it, there is no correlation
- Fitting trending time series data is difficult.
- [[republican]]" [On Regression for Pretense (and Unit Root Processes, Republics, etc.) - A Data Scientist Working in Roppongi's Blog](http://tjo.hatenablog.com/entry/2013/04/23/190417)
    - > When the original series ytyt is a non-stationary process and the difference series is a stationary process, the process is called a unit root process.
        - [[random walk]] is [[unit root process]].
    - The phenomenon of "feigned regression" (spurious regression)
        - If we regress a unit root process on a unit root process, we get a sham regression.
        - Regression of a time series of stock prices on a random walk yields a highly significant model with a high probability of significance.
        - take the difference
    - You can't take the difference if there is a republican portion.
            - Use [[vector error correction model]] (VECM)

- stochastic process
        - [[steady-state process]]
        - [[Autoregressive summed moving average]] process ([[ARIMA]])
        - [[vector autoregression]] process([[VAR]])

---
This page is auto-translated from [/nishio/時系列データ分析のメモ](https://scrapbox.io/nishio/時系列データ分析のメモ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.