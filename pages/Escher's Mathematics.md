---
title: "Escher's Mathematics"
---

[PDF](http://www.juen.ac.jp/math/nakagawa/openh26escher.pdf)
- 1: Flat tiling
- 2: Euclidean plane
- 3: Complex plane
- 4:  [[linear fractional transformation]]
- 5:  [[Poincaré disc]]

- Define the distance between two points a and b on the disk D as [$ d(a, b) = \log \frac{ 1 + |c| }{1 - |c|}
    - where $c(a, b) = \frac{b - a}{1 - \bar{a}b}$
            - [[linear fractional transformation]]
    - Especially when a=0 $d(0, b) = \log \frac{ 1 + |b| }{1 - |b|}$
- I want to find the distance between a=<r, -t> and b=<r, +t> for small t
    - b - a is $2ir\sin t$.
    - |b - a| is $2r\sin t$.
    - Since $|\bar{a}b|$ is the product of complex numbers of length r, r^2
    - (wrong) |c| = $2r\sin t / (1 - r^2)$
        - r is 0 to 1
        - Huh? If|c| exceeds 1, the denominator of d(a, b) will be negative, right? What did I do wrong?
        - Ah, not $1-|\bar{a}b|$, but $|1-\bar{a}b|$.
    - $|1-\bar{a}b|$ is the distance between <r^2, 2t> and 1, so $\sqrt{1 + r^4 -2 r^2 \cos t}$
    - Assuming cos t = 0.999, it looks like this
        - ![image](https://gyazo.com/221ad686b9a81ba6816aeb546771dbe2/thumb/1000)
        - Then sin t is about 0.045
    - ![image](https://gyazo.com/bdec1c35b17188af5e50cee13f72ac2a/thumb/1000)
        - It's still over 1. What's wrong yet?

- 6:  [[trigonometry]]
- 7: parallel and [[hyperparallel]].
- 8: Area of polygon
- 9: Tiling on [hyperbolic plane
---
This page is auto-translated from [/nishio/エッシャーの数学](https://scrapbox.io/nishio/エッシャーの数学) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.