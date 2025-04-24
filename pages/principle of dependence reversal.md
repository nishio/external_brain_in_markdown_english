---
title: "principle of dependence reversal"
---

Dependency inversion principle
- High-level modules should not depend on low-level modules. Both should depend on abstractions.
- Abstractions should not depend on details. Details should depend on abstractions.
[https://en.wikipedia.org/wiki/Dependency_inversion_principle](https://en.wikipedia.org/wiki/Dependency_inversion_principle)

- Upper-level modules should not depend on lower-level modules. Both should depend on [[abstract]].
- Abstract should not depend on details. Details should depend on abstractions.

Note that "upper level" does not mean "models with high [[abstraction]]".
- A module (i.e., a higher-level module) that uses a certain module X,
- It depends on the implementation details of X (i.e., it needs to change to match when the [[Implementation Details]] of X change),
- Will the upper level modules have to be changed every time module X is changed?
- Or there are dynamics at work that try to avoid changing module X because they don't like it.

- [[dependence reversal]]

---
This page is auto-translated from [/nishio/依存性逆転の原則](https://scrapbox.io/nishio/依存性逆転の原則) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.