---
title: "Definition of Strategic Resistance"
---

- Definition of [[strategicity]] from [[Mechanism Design (Book)]].

basic concept
Set of individuals $I = \{1, 2, \ldots, n \}$
- [[result]] set of $X$
- Often a set of viable resource allocations

Preference:$\succsim$
- Preference is used exclusively in the form $\succsim_i$ for the preference of individual i, but since i is irrelevant in the definition, the subscripts are omitted.
- Binary relations on X satisfying three conditions
        - [[reflectivity]] $\forall x \in X, x \succsim x$
        - [[transitive]] $\forall x, y, z \in X, x \succsim y \wedge y \succsim z \Rightarrow x \succsim z$
        - [[completeness]] 	$\forall x, y \in X, x \succsim y \vee y \succsim x$
- Related [[ordered set]].
    - In short, preference is [[universal sequential]] minus [[antisymmetric law]] (x=y if x is greater than y and y is greater than x).
        - [[previous-order]] with [completeness
        - > Usually, economics and game theory assume that preferences are pre-ordered - [Game Theory [[3rd ed.]]].
- Target part of the preference
- $\forall x,y \in X, x \sim y \Leftrightarrow x \succsim y \wedge y \succsim x$
- Asymmetric part of preference
- $\forall x,y \in X, x \succ y \Leftrightarrow x \succsim y \wedge y \not\succsim x$
- selection asymmetry
- $\forall x,y \in X, x \sim y \Leftrightarrow x = y$
    - No two opposites are preferred to the same degree.
    - This kind of preference is called "strong preference" (some call it linear preference, but it is not used in this book to avoid misunderstanding).

The set of all preferences on X $\mathscr{R}$
The preferences $\mathscr{D}_i \subseteq \mathscr{R}$ that individual i can take are called preference sets
- Although the formulation can vary from person to person, it can of course be identical, depending on the specific issue. For example, when considering voting for one of three candidates, the possible preferences of each individual are of course identical.
Preference for individual i: $\succsim_i \in \mathscr{D}_i$
- Binary relations are just elements of the "set of binary relations," but I'm getting parsing errors in my brain.
- The binary relation R on $X$ is just a subset of the ordered pair $X^2$ in the first place: $x R y \Leftrightarrow (x, y) \in R$.
Domain: $\mathscr{D}_I \equiv \mathscr{D}_1 \times \mathscr{D}_2 \times \cdots \times \mathscr{D}_n$
Preferred pairs: $\succsim \equiv (\succsim_1, \succsim_2, \ldots, \succsim_n) \in \mathscr{D}_I$
A social choice response is a non-empty response [$ F: \mathscr{D}_I \twoheadrightarrow X
- Domain to Consequences Response
- What is "correspondence" $\twoheadrightarrow$?
    - $F: X \twoheadrightarrow Y$ when $\forall x \in X, F(x) \subset Y$.
    - Compare with function
        - $f: X \rightarrow Y$ when $\forall x \in X, f(x) \in Y$.
    - If $F, G : X \twoheadrightarrow Y$ is $F \subseteq G \Leftrightarrow [F(x) \subseteq G(x) \forall x \in X]$ then F is called a "partial correspondence" of G
    - Call f a "selection" of F if $F : X \twoheadrightarrow Y, f: X \rightarrow Y$ is $f \in F \Leftrightarrow [f(x) \in F(x) \forall x \in X]$
- Non-empty means that the corresponding end area is not empty.
    - If it's empty, "None of the consequences are good!" which is inconvenient, probably.
- [[social choice function]]
- When the social choice correspondence F always gives one consequence, F is called [[social choice function]] and denoted by f.
    - To say that "the social choice correspondence F always gives one consequence" is $\forall \succsim \in \mathscr{D}_I, |F(\succsim)| = 1$.
- [[strategicity]] ( [[strategic inoperability]] )
- $\forall i\in I, \succsim \in \mathscr{D}_I, \succsim_i' \in \mathscr{D}_i, f(\succsim) \succsim_i f(\succsim_i', \succsim_{-i})$
- That is, for any preference group ($\succsim$), the following holds
    - If the preference $\succsim_i$ of one person i is replaced by another preference $\succsim_i'$, the resulting consequence $f(\succsim_i', \succsim_{-i})$ is not preferred by i to the consequence $f(\succsim)$ obtained when no replacement is made There is no
- For any individual i, lying and declaring a preference $\succsim_i'$ other than his or her true preference $\succsim_i$ will not lead to a more favorable outcome for him or her.
    - So people don't lie and file a tax return, right?
---
This page is auto-translated from [/nishio/耐戦略性の定義](https://scrapbox.io/nishio/耐戦略性の定義) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.