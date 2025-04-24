---
title: "Field hockey stick identity"
---

Field hockey Stick Identity:.
- $\sum_{i=0}^k \binom{n+i}{i} = \binom{n+k+1}{k}$

- proof
        - [[negative binomial theorem]]  eq4-1
        - $1/(1-x)^{d+1} = \sum_{n=0}^\infty \binom{n+d}{d}x^n$
        - [[Partial sum of coefficients of formal power series]]  eq4-2
        - $\displaystyle \sum_{i=0}^{k} [x^{i}]F =  [x^{k}] \frac{1}{1-x}F$
    - [[eq4-3]]
        - $\binom{n + m}{m} = \binom{n + m}{n}$
    - $\sum_{i=0}^k \binom{n+i}{i} = \sum_{i=0}^{k} [x^{i}] \sum_{m=0}^\infty \binom{n+m}{m}x^m$ ... Partial sum of coefficients
    - $\sum_{i=0}^{k} [x^{i}] \sum_{m=0}^\infty \binom{n+m}{m}x^m = [x^{k}] \frac{1}{1-x}\sum_{m=0}^\infty \binom{n+m}{m}x^m$ ... by eq4-2
    - $[x^{k}] \frac{1}{1-x}\sum_{m=0}^\infty \binom{n+m}{m}x^m = [x^{k}] \frac{1}{1-x}\sum_{m=0}^\infty \binom{n+m}{n}x^m$ ... by eq4-3
    - $[x^{k}] \frac{1}{1-x}\sum_{m=0}^\infty \binom{n+m}{n}x^m = [x^{k}] \frac{1}{1-x} \frac{1}{(1-x)^{n+1}} $ ... by eq4-1

    - $[x^{k}] \frac{1}{1-x} \frac{1}{(1-x)^{n+1}} = [x^{k}] \frac{1}{(1-x)^{n+2}}$ ... Sorting out

    - $[x^{k}] \frac{1}{(1-x)^{n+2}} = [x^{k}] \sum_{m=0}^\infty \binom{m+n+1}{n+1}x^n$ ... by eq4-1
    - $[x^{k}] \sum_{m=0}^\infty \binom{m+n+1}{n+1}x^n = \binom{k+n+1}{n+1}$ ... Coefficients of formal power series
    - $\binom{k+n+1}{n+1} = \binom{k+n+1}{k}$ ... by eq4-3
        - [Pascal's triangle
        - ![image](https://gyazo.com/cb5165171cd65ea576c0bb8ccad20320/thumb/1000)
        - [Hockey Stick Identity | Math for Thinking Skills](http://www.mathlion.jp/article/ar137.html)

- [[binomial coefficient formula]]
---
This page is auto-translated from [/nishio/ホッケースティック恒等式](https://scrapbox.io/nishio/ホッケースティック恒等式) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.