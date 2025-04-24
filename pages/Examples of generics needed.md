---
title: "Examples of generics needed"
---

Minimal code to reproduce the problem
ts

```typescript
type X = "A" | "B";
const f = (x: X): X => (x);
const a: "A" = f("A");  // error
```


error
- Type 'X' is not assignable to type '"A"'.
    - Type '"B"' is not assignable to type '"A"'

solution
ts

```typescript
const f = <T extends X>(x: T): T => (x);
const a: "A" = f("A");  // ok
```


- [[generics]]  [[TypeScript]]
[Using Type Parameters in Generic Constraints](https://www.typescriptlang.org/docs/handbook/generics.html#using-type-parameters-in-generic-constraints)

---
This page is auto-translated from [/nishio/ジェネリクスが必要な例](https://scrapbox.io/nishio/ジェネリクスが必要な例) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.