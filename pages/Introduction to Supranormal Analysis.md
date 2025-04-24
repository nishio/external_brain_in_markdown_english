---
title: "Introduction to Supranormal Analysis"
---

![image](https://gyazo.com/5981154568d2eb85013f2cfc89b00459/thumb/1000)
- [Amazon](https://amzn.to/2LVxYaj)
    - [[super-level analysis]]
    - [[infinitesimal]]

1: Set
- Set $\Gamma$ to [[addend]] [[set of related or similar families]].
    - [[valid expression]]
- Any set can be expressed as $S = \{x \in U | \phi(x) \}$ using some logical formula [$ \phi
        - [[separator axiom]]

2:  [[concentration]]
    - [[Cantor's theorem]]
- $|N| < |P(N)|$
        - [[continuum hypothesis]] $|N| < |A| < |P(N)|$ there exists no A such that
        - Proven "not provable from [[ZFC]]."
3:  [[Bernstein's theorem]]
- Let sets A and B be infinite sets; if there is a 1:1 correspondence f from A to a subset of B and a 1:1 correspondence g from B to a subset of A, then there is a 1:1 correspondence between A and B
4:  [[axiomatic set theory]]
5:  [[axiom of choice]]
6:  [[Weierstrass' theorem]]
- If a subset A of R is bounded above, then there exists an upper bound sup A of A. If A is bounded below, then there exists a lower bound inf A of A.
7, 8: Composition of [[real number]] by [Cauchy column
    - [[convergent sequence]]
- Cauchy column
    - $\forall \varepsilon > 0 \quad \exists N \in \mathbb{N} \quad \forall p, q \in \mathbb{N} \quad(p > q > N → |a_p - a_q| < \varepsilon)$
- Convergent columns are Cauchy columns
- That a Cauchy sequence is a convergent sequence is shown in 13.3 using [super-level analysis
- Use a Cauchy sequence consisting of rational numbers to construct real numbers
    - [[rational Cauchy sequence]]
    - $\forall \epsilon \in \mathbb{Q}^+ \quad \exists N \in \mathbb{N} \quad \forall p, q \in \mathbb{N} \quad(p > q > N → |a_p - a_q| < \varepsilon)$
    - Let $\mathbb{Q}^\#$ be the set of rational Cauchy sequences
- For rational Cauchy sequences a_n, b_n $\lim_{n\to\infty} (a_n - b_n) = 0$ is an equivalence relation
    - We can create a quotient set with this equivalence relation from a set of favorable Cauchy sequences.
    - This set looks like real numbers.
    - [[ordering system]]
    - Use with 10
9:  [[Fraiche Filter]]
- filter (esp. camera)
    - A family $F \subset P(N)$ of subsets of the whole set N of natural numbers is called a filter on N if F satisfies the following conditions
        - 1:$N \in F$
        - 2: $0 \notin F$
        - 3: $(A \in F \wedge A \subset B) \to B \in F$
            - Sets with subsets that are contained in the filter are contained in the filter
        - 4: $(A \in F \wedge B \in F) \to A \cap B \in F$
            - The common subset of the two sets contained in the filter is contained in the filter
    - In addition, if the following conditions are met, it is called a super filter
        - 5: $\forall A \subset N (A \in F \vee A^c \in F)$
            - For any subset A, A is contained in F or the complement of A
                - <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Can both be included?
                    - If both A and the complement of A are contained, then by (4) their common subset 0 is also contained in F, but this violates (2). Therefore, both cannot be included.

    - [[Fraiche Filter]]
- $\mathcal{F}_0 = \{ A \subset \mathbb{N} | A^c is a finite set \}$


- Create a quotient set from a set of real sequences by equivalence relation using [Fraiche Filter
    - [[less than sign or greater than sign (]] used in the definition of
    - [[super filter]]
10: [[hyperreal number]] configuration
11:  [[supernatural number]]
    - [[infinity]]
    - A hyperreal number r such that $|r|>n$ for any standard natural number n is called an infinite number.
    - [[infinite decimals]]
    - A hyperreal number r such that $|r|<1/n$ for any standard natural number n is called an infinite fraction
    - Existence of non-zero infinitesimals
        - Example: $[(1, 1/2, 1/3, \ldots)$]
        - Need $\{n+1, n+2, \ldots\} \in \mathcal{F}$ to say that this is an infinite fraction
        - Theorem D.4 p.106
            - When F is a superfilter on N, "F contains no finite set" and "F contains F0" are equivalent
            - F0 means Freshet filter
            - Definition of Flesché filter p.38
            - $\mathcal{F}_0 = \{ A \subset \mathbb{N} | A^c is a finite set \}$
            - The proof itself is simple.
            - If we can show that "the ultrafilter contains F0", we can say [$ \{n+1, n+2, \ldots\} \in \mathcal{F}
                - Because the complement set is a finite set.
        - For a while, I was wondering "How can we show that the super filter contains F0?
            - The idea was backwards, the super filter does not necessarily include F0
        - Theorem D.5 "For any filter F there exists a superfilter containing F"
            - There can be more than one super filter.
            - Indicates "the existence of a superfilter containing the Fréchet filter F0."
            - Use [[Zorn's Supplement]] for this proof

    - [[Near Infinite]]
    - When x-y is an infinite fraction, x and y are "near infinite".
    - [[(philosophical) monad]]
    - For some real number x, the set of near-infinite hyperreal numbers y is called the monad of x
12, 13: [[limit]] of a sequence of numbers
- Defined without [$ \epsilon-calculated-delta
- $\lim_{n\to\infty} a_n = a$
- $\forall n \in *\mathbb{N}_\infty (*a_n \approx a)$
    - For an infinite natural number n, a_n is infinitely close to a
14
- st: operation to create a standard real number, definition on p. 49
15, 16: [[consecutive]] function
17: Differentiation
- Divide by a non-zero infinite decimal
18, 19: Integration by hyperquadratic analysis

---
This page is auto-translated from [/nishio/超準解析入門](https://scrapbox.io/nishio/超準解析入門) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.