---
title: "elliptic curve"
---

$y^{2}=x^{3}+ax+b$
- The explanation that (a, b) satisfying this forms a group is incorrect.
    - Need to add infinity point O
    - We can make this infinite point O a group by defining the addition in a clever way so that it is the unit source

tasty addition
- $s = \frac{y_P - y_Q}{x_P - x_Q}$
- $x_{R} =s^{2}-x_{P}-x_{Q}$
- $y_{R} =y_{P}+s(x_{R}-x_{P})$
- This addition, of course, will result in the denominator of s being zero when xP = xQ
    - So then we define P + Q = O

The definition of this addition does not include a or b
- Therefore, if there exists an "oracle that receives P and returns nP", then nP is obtained for any point P on any elliptic curve
- By standard, elliptic curves are chosen because it is difficult to make n from (P, nP)
    - However, it is possible to obtain (P, nP) on a curve that is easy to compute
    - We just need to verify that the P passed is a point on the assumed curve, but most Bluetooth devices do not verify this.

---
This page is auto-translated from [/nishio/楕円曲線](https://scrapbox.io/nishio/楕円曲線) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.