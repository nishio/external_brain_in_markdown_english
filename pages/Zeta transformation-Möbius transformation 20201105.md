---
title: "Zeta transformation/Möbius transformation 20201105"
---

- [[zeta transformation]] / [[Moebius transform]] Notes on what I thought
- Note: These notes are in the process of being finalized and may contain errors.

    - [[Riemann's zeta function]]
    - $\zeta (s)=\sum^{\infin}_{n=1} \frac{1}{n^s}$
    - This is a kind of Dirichlet series ([Dirichlet series
            - [[Dirichlet series]] :
            - $D_A(s) = \sum^{\infin}_{n=1} \frac{A_i}{n^s}$
        - [[Dirichlet product]]
        - The product of a Dirichlet series and the convolution on the product of a sequence of numbers correspond
        - $D_A(s)D_B(s) = D_C(s) \iff C_k = \sum_{ij=k} A_iB_j$
    - Inverses and Möbius functions in the Dirichlet product of zeta functions
        - $\frac{1}{\zeta (s)}= \sum^{\infin}_{n=1} \frac{\mu(n)}{n^s}$
        - where $\mu(n)$ is the [[Möbius function]].
    - Can create [[irreducible sum function]] from zeta function (how?)

    - [Mathematics Introduction to Convolution: Dirichlet Products and Zeta and Mobius Transforms | maspy's HP [https://maspypy.com/%E6%95%B0%E5%AD%A6-%E7%95%B3%E3%81%BF%E8%BE%BC%E3%81%BF%E5%85%A5%E9%](https://maspypy.com/%E6%95%B0%E5%AD%A6-%E7%95%B3%E3%81%BF%E8%BE%BC%E3%81%BF%E5%85%A5%E9%) 96%80%EF%BC%9Adirichlet%E7%A9%8D%E3%81%A8%E3%82%BC%E3%83%BC%E3%82%BF%E5%A4%89%E6%8F%9B%E3%83%A1%E3%83%93%E3%82%A6]
    - Zeta/Möbius functions in [adjacent algebra
    - Adjacency algebra: a bounded polytope ring defined over a commutative ring with any locally finite semi-ordered set and unitary source (what?).
        - [Adjacent algebra (Order theory) - Wikipedia](https://ja.wikipedia.org/wiki/%E9%9A%A3%E6%8E%A5%E4%BB%A3%E6%95%B0_(%E9%A0%86%E5%BA%8F%E7%90%86%E8%AB%96))
        - Specifically, the power set of a set, etc.
    - The source of the adjacency algebra is a function that maps a scalar f(a, b) to each nonempty interval $[a, b$]
    - The "product" of adjoint algebras is defined by the following convolution
        - $(f*g)(a,b)=\sum _{{a\leq x\leq b}}f(a,x)g(x,b)$
    - ![image](https://gyazo.com/4d08557f6dce39a5282eaefb61b9e142/thumb/1000)

    - Now consider the product of some f and the zeta function
        - $(f*\zeta)(a,b)=\sum _{{a\leq x\leq b}}f(a,x)\zeta(x,b) = \sum _{{a\leq x \leq b}}f(a,x)$
        - This is a cumulative sum(?)
        - If we write $f(0, x)$ as [$ F_x
        - $(F*\Zeta)_b = (f*\zeta)(0,b) =  \sum_{{0\leq x \leq b}}f(0,x) = \sum _{{0\leq x \leq b}}F_x$
            - Sure, this looks cumulative Japanese-ish, but...
    - [Cumulative Sum and Zeta Transform - masu-mi's blog(Dirty Cache)](https://blog.masu-mi.me/post/2020/06/08/comulative-and-zeta-transoform/)
- These two worlds are not unrelated.
    - They are (REALLY?) connected by the relationship "convolution of a sequence is a product of Dirichlet series."
- When the topic of the envelopment principle brings up fast Möbius transforms, it is often the case that sum over subsets
    - $\sum_{T\subset S} f(T)$
    - Hard to see the connection between this and the story so far.
        - Any natural number n such that the value of [[Möbius function]] is nonzero can be regarded as a set.
        - It only contains at most one of each prime factor.
    - Then, the sum over the divisor of n can be equated with the sum over the subset.
        - $\sum_{T\subset S} f(T) = \sum_{d|N} f'(d)$
- In other words, the reason I thought "I don't understand" at first was because the three concepts that were not self-evidently identical to me were called by one word, and once I clarified each of them and clarified the method of correspondence, I felt that I "understood" them. In other words, my initial "I don't understand" was due to the fact that three concepts that were not self-identical to me were called by one word, and once I clarified each of them and clarified the method of correspondence, I felt that I "understood" them.

- Now unresolved points
    - Without mentioning the adjacency algebra, if you transform the convolution with the Riemann zeta into an expression, doesn't it take the form of a cumulative sum?
    - Adjacent Algebra Order
        - Inclusion of sets is semi-ordered
        - The "is approximately" relation of the natural numbers is semi-ordered

Mapping sets to natural numbers
- ![image](https://gyazo.com/4bbea44cb7446cc878ddbf4d856ae884/thumb/1000)
- We can see that the inclusion relation between sets corresponds to the "is approximately" relation between natural numbers

There is one on natural numbers, one on sequences and Dirichlet series, and one on sets.
The Mobius inversion formula also looks a little different.

- [[Inclusion-Desclusion Principle and Möbius Inversion Formula]]

- [[Sum of Möbius functions]]

![image](https://gyazo.com/36e8a4ecef5776989e3335ccd44cedad/thumb/1000)
[https://ja.wikipedia.org/wiki/隣接代数_(order-theory)](https://ja.wikipedia.org/wiki/隣接代数_(order-theory))

---
This page is auto-translated from [/nishio/ゼータ変換/メビウス変換20201105](https://scrapbox.io/nishio/ゼータ変換/メビウス変換20201105) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.