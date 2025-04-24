---
title: "ARC110D_FPS"
---

![image](https://gyazo.com/829c06c94c53cc49c05c234e5f3445c5/thumb/1000)
[D - Binomial Coefficient is Fun](https://atcoder.jp/contests/arc110/tasks/arc110_d)

Solve [[ARC110D]] by attributing it to [formal power series

$F_{i}(x) = \sum_{k=0}^{\infty} \binom{k}{A_{i}} x^{k}$
$ G(x) = \prod_{i=1}^{N} F_{i}(x)$
    - [[Lower fixed binomial coefficient → negative binomial theorem]] :
    - $\binom{A+i}{A} = [x^i] \sum_n \binom{A+n}{A}x^n = [x^i]\frac{1}{(1-x)^{A+1}} $
- $i < 0$, since $\binom{A+i}{A} = 0$ $F_{i}(x) = \sum_{k=0}^{\infty} \binom{k}{A_{i}} x^{k} = \frac{x^{A_i}}{(1-x)^{A_i+1}}$

$S := \sum A_i$

$ G(x) = \prod_{i=1}^{N} F_{i}(x) = \frac{x^S}{(1-x)^{S+N}}$

    - [[Partial sum of coefficients of formal power series]] :
- $\displaystyle \sum_{i=0}^{k} [x^{i}]F =  [x^{k}] \frac{1}{1-x}F$

$X = \sum_{i=}^{M} [x^{i}]G =  [x^{M}] \frac{1}{1-x}G = [x^{M}]\frac{x^S}{(1-x)^{S+N+1}}$
$= [x^{M-S}]\frac{1}{(1-x)^{S+N+1}}$

    - [[Power series → binomial coefficient]] :
    - $[x^B]\frac{1}{(1-x)^{A}} = \binom{A+B-1}{A-1}$

$[x^{M-S}]\frac{1}{(1-x)^{S+N+1}} = \binom{S+N+1+M-S-1}{S+N} = \binom{N+M}{S+N}$


reference
- [https://maspypy.com/atcoder-参加感想-2020-12-06arc110](https://maspypy.com/atcoder-参加感想-2020-12-06arc110)
    - Almost the flow of this
- [https://twitter.com/kyopro_friends/status/1335227103797673984?s=21](https://twitter.com/kyopro_friends/status/1335227103797673984?s=21)
- [https://twitter.com/maspy_stars/status/1335225085255319556?s=21](https://twitter.com/maspy_stars/status/1335225085255319556?s=21)
- [https://scol.hatenablog.com/entry/2020/12/06/015509](https://scol.hatenablog.com/entry/2020/12/06/015509)

---
This page is auto-translated from [/nishio/ARC110D_FPS](https://scrapbox.io/nishio/ARC110D_FPS) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.