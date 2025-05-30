---
title: "circle"
---

Circle C consists of the following: (1)
- Subject [[kind]] ob(C)
- The analogue of [[arrow]] hom(C) between the subject
    - Each projection f ∈ hom(C) is accompanied by an object a ∈ ob(C), called the starting region, and an object b ∈ ob(C), called the ending region, and we say that "f is the projection from a to b" and write f: a → b.
- The class of the projection from a to b (hom-class; hom class) hom(a, b) is the class formed by the whole projection from a to b.

Then, for any three objects a, b, c ∈ ob(C), there exists a binary operation hom(a, b) × hom(b, c) → hom(a, c); (f, g) ↦ g ∘ f called the composition of arrays, satisfying the following axioms: .
- If the coupling laws: f: a → b, g: b → c, h: c → d then h ∘ (g ∘ f) = (h ∘ g) ∘ f holds.
- Unit rule: for each object x ∈ ob(C)
    - There exists a self-projection $id_x = 1_x: x → x$ called the identity projection of x,
    - For any arrays f: a → x and g: x → b, $1_x ∘ f = f$ and $g ∘ 1_x = g$.

[Sphere (mathematics) - Wikipedia](https://ja.wikipedia.org/wiki/%E5%9C%8F_(%E6%95%B0%E5%AD%A6))

Comparison with monoid
|  | Sphere [[monoid]]. |
| -- | -- | -- |
|  | Target class ob(C) Set S |
|  | Composition of projectiles Multiplication |
| * | hom(a, b) × hom(b, c) → hom(a, c) | S × S → S |
|  | associative law |
|  | Existence of identity projection Existence of unitary source |

---
This page is auto-translated from [/nishio/圏](https://scrapbox.io/nishio/圏) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.