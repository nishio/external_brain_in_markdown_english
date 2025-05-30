---
title: "Using a limited set of string literals"
---

en [https://basarat.gitbook.io/typescript/type-system/index-signatures#using-a-limited-set-of-string-literals](https://basarat.gitbook.io/typescript/type-system/index-signatures#using-a-limited-set-of-string-literals)
ja [https://typescript-jp.gitbook.io/deep-dive/type-system/index-signatures#riteraruwosuru](https://typescript-jp.gitbook.io/deep-dive/type-system/index-signatures#riteraruwosuru)
Using a limited set of string literals
Use a limited number of string literals
An index signature can require that index strings be members of a union of literal strings by using Mapped Types e.g.:
By using the map type, we can create an index signature that requires the index string to be a member of the "union type of literal character type".

This is often used together with keyof typeof to capture vocabulary types, described on the next page.
To obtain the lexical type of a dictionary, keyof typeof is often used together, which will be explained on the next page.
The specification of the vocabulary can be deferred generically:
Vocabulary specification can be done later by using generics.


ts

```typescript
type K = "A" | "B" | "C";
const x1: { [k in K]: number } = { A: 1, B: 2, C: 3 }; // OK
// const x2: { [k in K]: number } = { A: 1, B: 2 }; // NG: Property 'C' is missing
const x3: { [k in K]?: number } = { A: 1, B: 2 }; // OK
// const x4: { [k in K]: number } = { A: 1, B: 2, C: 3, D: 4 };
// NG: Object literal may only specify known properties, and 'D' does not exist
```



---
This page is auto-translated from [/nishio/Using a limited set of string literals](https://scrapbox.io/nishio/Using a limited set of string literals) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.