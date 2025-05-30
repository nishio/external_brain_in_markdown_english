---
title: "TypeScript Type"
---

structual subtyping

interface
- Error if there is no declared property
- Error if there are undeclared properties
- Optional: No need to

union
- It can be one of the two

intersection
- Intersection types have the following subtype relationships:
    - An intersection type I is a subtype of a type T if any type in I is a subtype of T.
    - A type T is a subtype of an intersection type I if T is a subtype of each type in I.
- Similarly, intersection types have the following assignability relationships:
    - An intersection type I is assignable to a type T if any type in I is assignable to T.
    - A type T is assignable to an intersection type I if T is assignable to each type in I.



- [https://stackoverflow.com/questions/37233735/typescript-interfaces-vs-types](https://stackoverflow.com/questions/37233735/typescript-interfaces-vs-types)
- type does not create an instance of a new type, but simply aliases it to another type
    - Some people are confused when they create an alias for an object literal type because it looks like an INTERFACE
---
This page is auto-translated from [/nishio/TypeScriptのType](https://scrapbox.io/nishio/TypeScriptのType) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.