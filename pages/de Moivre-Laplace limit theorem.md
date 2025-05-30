---
title: "de Moivre-Laplace limit theorem"
---


- $B(k; n, p) \approx \frac{1}{\sqrt{2\pi n p q}} \exp\left\{ - \frac{(k - np)^2}{2npq} \right\}$

- Theorem that the binomial distribution $B(n, p)$ approaches a normal distribution with [$ n \to \infty
- Discovered by [[de moivre]] in 1733.
    - At that time, the term normal distribution did not yet exist.
    - Gauss was born in 1777.
    - de moivre amazing!
- Later generalized to produce the central limit theorem
- I want to make sure I understand the flow of this binomial distribution whose limit is the normal distribution.

- For a random variable $X \sim B(n, p)$ following a binomial distribution [$ B(n, p)
- $P(X=k) = \frac{n!}{k!(n-k!)} p^k (1-p)^{n-k}$
- For simplicity, let $q = 1 - p$.
- $P(X=k) = \frac{n!}{k!(n-k!)} p^k q^{n-k}$
- We want to show that the following approximation holds when this $n$ is large
- $P(X=k) \approx \frac{1}{\sqrt{2\pi n p q}} \exp\left\{ - \frac{(k - np)^2}{2npq} \right\}$

- Since it is troublesome if k is fixed while n grows, we put $k = np + x\sqrt{npq}$.
    - That is, $x = \frac{k - np}{\sqrt {npq}}$
    - $\frac{1}{\sqrt{2\pi n p q}} \exp\left\{ - \frac{(k - np)^2}{2npq} \right\}$
    - $= \frac{1}{\sqrt{2\pi n p q}} \exp\left\{ - \frac{(x\sqrt{npq})^2}{2npq} \right\}$
    - $= \frac{1}{\sqrt{2\pi n p q}} \exp\left\{ - \frac{x^2 npq}{2npq} \right\}$
    - $= \frac{1}{\sqrt{2\pi n p q}} \exp\left\{ -\frac{x^2}{2} \right\}$

    - Using [Sterling's formula
    - Stirling's formula is an approximation of factorials by powers
    - $n! \approx n^n e^{-n} \sqrt{2\pi n}$
    - Here comes the familiar $2 \pi$!

Proof from here
- $P(X=k) = \frac{n!}{k!(n-k!)} p^k q^{n-k}$
    - Eliminate factorials using Stirling's formula
- $\approx \frac{n^n e^{-n} \sqrt{2\pi n} }{  k^k e^{-k} \sqrt{2\pi k} \cdot (n-k)^{n-k} e^{-(n-k)} \sqrt{2\pi (n-k)}   } p^k q^{n-k}$

    - Sort it out.
- $= \frac{e^{-n} \sqrt{2\pi n} }{ e^{-k} \sqrt{2\pi k} \cdot e^{-(n-k)} \sqrt{2\pi (n-k)}}  \frac{n^n}{k^k \cdot (n-k)^{n-k}}  p^k q^{n-k}$

    - About the first half
        - The first half of this equation
        - $\frac{e^{-n} \sqrt{2\pi n} }{ e^{-k} \sqrt{2\pi k} \cdot e^{-(n-k)} \sqrt{2\pi (n-k)}}$
        - and
        - $\frac{1}{\sqrt{2\pi n p q}}$
        - to be the case.

        - $\frac{e^{-n} \sqrt{2\pi n} }{ e^{-k} \sqrt{2\pi k} \cdot e^{-(n-k)} \sqrt{2\pi (n-k)}}$
        - $= \frac{\sqrt{2\pi n} }{ \sqrt{2\pi k} \cdot \sqrt{2\pi (n-k)}}$
        - $= \frac{\sqrt{n} }{ \sqrt{2\pi k (n-k)}}$
        - $= \frac{1}{ \sqrt{2\pi n \frac{k}{n} \frac{n-k}{n} }}$
        - where $n$ is large because [$ k/n \approx p
        - $\approx \frac{1}{ \sqrt{2\pi n p q }}$
        - Now we have the first half of the equation we want to get.
        - another solution
            - [[de Moivre-Laplace limit theorem#595f4cccaff09e00009aa3e0]]

    - reprint
- $P(X=k) \approx \frac{1}{\sqrt{2\pi n p q}} \exp\left\{ - \frac{(k - np)^2}{2npq} \right\}$

    - About the second half
        - Second half of the equation
        - $\frac{n^n}{k^k \cdot (n-k)^{n-k}}  p^k q^{n-k}$
        - and
        - $\exp\left\{ - \frac{(k - np)^2}{2npq} \right\} =  \exp\left\{ -\frac{x^2}{2} \right\}$
        - to be the case.

        - I'll try to form exp first.
        - $\frac{n^n}{k^k \cdot (n-k)^{n-k}}  p^k q^{n-k}$
        - $= \frac{n^k \cdot n^{n-k}}{k^k \cdot (n-k)^{n-k}}  p^k q^{n-k}$
        - $= \left( \frac{np}{k} \right) ^ k \cdot \left( \frac{nq}{n - k} \right) ^ {n - k}$
        - $= \exp\left\{  \log\left\{  \left( \frac{np}{k} \right) ^ k \cdot \left( \frac{nq}{n - k} \right) ^ {n - k}   \right\}   \right\}$
        - $=  \exp\left\{ \log\left\{ \left( \frac{np}{k} \right) ^ k \right\} +  \log\left\{ \left( \frac{nq}{n - k} \right) ^ {n - k}  \right\} \right\}$

        - where $k = np + x\sqrt{npq}$, so
        - $\frac{k}{np} = \frac{np + x\sqrt{npq}}{np} = 1 + x \frac{q}{\sqrt{np}}$
        - $\frac{n - k}{nq} = \frac{n - np - x\sqrt{npq}}{nq}  = \frac{n(1 - p) - x\sqrt{npq}}{nq} = \frac{nq - x\sqrt{npq}}{nq}  = 1 - x \frac{p}{\sqrt{nq}}$

        - Substituting
        - $\exp\left\{ \log\left\{ \left( \frac{np}{k} \right) ^ k \right\} +  \log\left\{ \left( \frac{nq}{n - k} \right) ^ {n - k}  \right\} \right\}$
        - $= \exp\left\{ -k \log\left(  \frac{k}{np}  \right) +  (k - n) \log\left(  \frac{n - k}{nq}   \right) \right\}$
        - $= \exp\left\{ -k \log\left( 1 + x \frac{\sqrt q}{\sqrt{np}} \right) +  (k - n) \log \left( 1 - x \frac{\sqrt p}{\sqrt{nq}} \right) \right\}$

        - log is approximated up to the second order by [Taylor expansion
            - $\log(1+x) \approx x - {1 \over 2} x^2$
            - $\log(1-x) \approx -x - {1 \over 2} x^2$
        - Use this.
        - $\exp\left\{ -k \log\left( 1 + x \frac{\sqrt q}{\sqrt{np}} \right) +  (k - n) \log \left( 1 - x \frac{\sqrt p}{\sqrt{nq}} \right) \right\}$
        - $\approx \exp\left\{ -k \left( x \frac{\sqrt q}{\sqrt{np}} -  \frac{x^2q}{2np} \right) +  (k - n) \left( -x \frac{\sqrt p}{\sqrt{nq}} - \frac{x^2 p}{nq} \right) \right\}$

        - delete "k" characters
        - $k = np + x\sqrt{npq}$
        - $k - n = np + x\sqrt{npq} - n = n(p - 1) + x\sqrt{npq} = -nq + x\sqrt{npq}$
        - Expand each of the above terms, but ignore the third-order terms in x at this time
        - $-(np + x\sqrt{npq}) \left( x \frac{\sqrt q}{\sqrt{np}} - \frac{x^2q}{2np} \right) \approx -\left( x \sqrt{ npq} + x^2q - \frac{x^2q}{2}\right)$
        - $(-nq + x\sqrt{npq}) \left( -x \frac{\sqrt p}{\sqrt{nq}} - \frac{x^2p}{2nq} \right) \approx \left( x \sqrt{ npq} - x^2p + \frac{x^2q}{2}\right)$
        - Since these two add up to
        - $-\left( x \sqrt{ npq} + x^2q - \frac{x^2q}{2}\right) + \left( x \sqrt{ npq} - x^2p + \frac{x^2q}{2}\right)$
        - $= - \frac{x^2q}{2} - \frac{x^2q}{2}$
        - $= - \frac{x^2}{2}$

    - Thus, the second-order approximation shows that the following holds
    - $\frac{n^n}{k^k \cdot (n-k)^{n-k}}  p^k q^{n-k} \approx \exp\left\{ -\frac{x^2}{2} \right\} = \exp\left\{ - \frac{(k - np)^2}{2npq} \right\}$


Separate solution (broke my heart in the process)
- Branching from here [$ \frac{\sqrt{n} }{ \sqrt{2\pi k (n-k)}}
    - Erase k $k = np + x\sqrt{npq}$, $k - n = np + x\sqrt{npq} - n = n(p - 1) + x\sqrt{npq} = -nq + x\sqrt{npq}$
    - $\frac{\sqrt{n} }{ \sqrt{2\pi k (n-k)}} = \frac{\sqrt{n} }{ \sqrt{2\pi (np + x\sqrt{npq})(nq - x\sqrt{npq})}}$
    - $= \frac{\sqrt n}{\sqrt{2\pi n^2 (p + n\sqrt{pq}/\sqrt n )(q - x\sqrt{pq}/\sqrt n )  }}$
    - $= \frac{1}{\sqrt{2\pi n (p + n\sqrt{pq}/\sqrt n )(q - x\sqrt{pq}/\sqrt n )  }}$
    - $= \frac{1}{\sqrt{2\pi n p (1 + n\sqrt{q}/\sqrt{np} ) q (1 - x\sqrt{p}/\sqrt{nq} )  }}$
    - $= \frac{1}{\sqrt{2\pi n p q (1 + x\sqrt{q}/\sqrt{np} ) (1 - x\sqrt{p}/\sqrt{nq} )  }}$

    - Put this expression as A. Take the logarithm of A
    - $\log A = -\frac{1}{2} \left\{ \log(2\pi npq) + \log(1 + B) + \log(1 - C)\right\}$
        - For ease of description, we define $B = x\sqrt{q}/\sqrt{np}, C = x\sqrt{p}/\sqrt{nq}$.
    - where $0 < \theta, \theta' < 1$, which is due to [[Lagrange's mean value theorem]], exists and
    - $\log(1 + B) + \log(1 - C) = B / (1 + \theta B) - C / (1 - \theta' C)$
    - Consider the possible range of absolute values of this value
    - Note that x is minimal and $-np / \sqrt{npq}$, then $B = -1, C = -p/q$.
    - Note that x is at most $nq / \sqrt{npq}$, then $B = q/p, C = 1$
    - I'd like to say $\log A = -\frac{1}{2} \log(2\pi npq)$ by showing that the absolute value converges to 0 as n increases, but I haven't done it yet.


- ref
    - [https://en.wikipedia.org/wiki/De_Moivre%E2%80%93Laplace_theorem](https://en.wikipedia.org/wiki/De_Moivre%E2%80%93Laplace_theorem)
---
This page is auto-translated from [/nishio/ド・モアブル=ラプラスの極限定理](https://scrapbox.io/nishio/ド・モアブル=ラプラスの極限定理) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.