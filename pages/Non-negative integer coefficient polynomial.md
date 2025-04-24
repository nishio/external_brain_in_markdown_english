---
title: "Non-negative integer coefficient polynomial"
---

> [Interesting issue I learned about today
>  A has one non-negative integer coefficient polynomial f(x) in mind.
>  You can tell Mr. A an integer a of your choice in one operation and have Mr. A tell you the value f(a) with a substituted for f(x).
>  How many operations at least would it take to determine f(x)?
[https://twitter.com/4p_t/status/1179331980305031169](https://twitter.com/4p_t/status/1179331980305031169)

2 times.
First, f(1) = a is obtained. This is the sum of all coefficients.
The fact that the coefficients are non-negative indicates that each coefficient does not exceed a.
Then f(n) is obtained for any integer n greater than a.
Since each coefficient is non-negative and an integer of at most a, f(n) corresponds to placing each coefficient at each digit of the n-decimal notation.
So we can find all the coefficients by dividing by n and repeating the process of taking the remainder.

---
This page is auto-translated from [/nishio/非負整数係数の多項式](https://scrapbox.io/nishio/非負整数係数の多項式) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.