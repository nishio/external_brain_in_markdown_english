---
title: "general term of a sequence"
---

I have chewed up [yukicoder No.42 Sigh of the piggy bank | maspy's HP](https://maspypy.com/yukicoder-no-42-%e8%b2%af%e9%87%91%e7%ae%b1%e3%81%ae%e6%ba%9c%e6%81%af) for my own understanding. I chewed it up for my own understanding.

When a formal power series F is of the form
$F = \frac{P}{(1-x^N)^M}$
The sequence of numbers for which this power series is taken by skipping N corresponding sequences
$\{{[x^{r+iN}]F}\} \quad (0 \le r < N)$
The general term of can be expressed by the M-1st order equation

explanation
$P = p_0 + p_1 x + p_2 x^2 + p_3 x^3 + \ldots$
each term of x is classified by the remainder of the order of x divided by N.
- Example of N=2
    - $p_0 +  p_2 x^2 +  \ldots$
    - $p_1 x + p_3 x^3 + \ldots = x(p_1 + p_3 x^2 + \ldots)$
Express this in terms of N new proper series [$ P_r
- Example of N=2
    - $P_0(x^2)$
    - $xP_1(x^2)$
    - Representation in number sequences
    - $P_0: \{p_0, p_2, \ldots \}$
    - $P_1: \{p_1, p_3, \ldots \}$

Since $P = \sum_r x^r P_r(x^N)$
$F = \sum_r x^r \frac{P_r(x^N)}{(1-x^N)^M}$
- Example of N=2
    - $F = \frac{P_0(x^2)}{(1-x^2)^M} + x\frac{P_1(x^2)}{(1-x^2)^M}$

Represent F in terms of a new N power series Fr
$F_r(x) = \frac{P_r(x)}{(1-x)^M}$
$F(x) = \sum_r x^rF_r(x^N)$
I don't know from here.
- I'd have to do the math on a real example to get the M-1st order formula.
    - For terms above the order of P.
![image](https://gyazo.com/e37b95d27289742db624c1e0f99a2908/thumb/1000)
What exactly do you do when you are given a p
    - [[polynomial interpolation]]
- Complementary formula for Lagrange?
    - [https://mathtrain.jp/hokan](https://mathtrain.jp/hokan)

---
This page is auto-translated from [/nishio/数列の一般項](https://scrapbox.io/nishio/数列の一般項) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.