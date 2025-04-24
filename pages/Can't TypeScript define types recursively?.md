---
title: "Can't TypeScript define types recursively?"
---

- [[TypeScript types]]

summary
- With named types like interface, tree definitions, etc. could be done before.
- Since 3.7, type alias can be done in some cases.
- But we can't define recurrently in the way we wanted to do it this time.
- You can't even make it an INTERFACE.
- Resolution [[Create natural numbers with TypeScript types]].

I just wanted to add...
ts

```typescript
type N0 = [];
type succ<N> = [any, N];
type N1 = succ<N0>
type N2 = succ<N1>
type N3 = succ<N2>
type pred<N> = N extends [any, infer R] ? R : never;
type NEQUAL<Na, Nb> = Na extends Nb ? any : never;
type testNEQUAL = NEQUAL<pred<N2>, succ<N0>>  // any
type add<Na, Nb> = Nb extends N0 ? Na : add<succ<Na>, pred<Nb>>
// Type alias 'add' circularly references itself.
```


[https://stackoverflow.com/questions/36966444/how-to-create-a-circularly-referenced-type-in-typescript](https://stackoverflow.com/questions/36966444/how-to-create-a-circularly-referenced-type-in-typescript)
[https://github.com/microsoft/TypeScript/pull/33050](https://github.com/microsoft/TypeScript/pull/33050)
[[TypeScript]] In 3.7
ts

```typescript
type ValueOrArray<T> = T | Array<ValueOrArray<T>>;  // OK
type ValueOrArray<T> = T | ValueOrArray<Array<T>>;  // NG
```


ts

```typescript
type add<Na, Nb> = Nb extends N0 ? Na : add2<Na, Nb>;
interface add2<Na, Nb> extends add<succ<Na>, pred<Nb>> { };  // NG
// An interface can only extend an object type or intersection of object types with statically known members.
```


---
This page is auto-translated from [/nishio/TypeScriptは型を再帰的に定義できない？](https://scrapbox.io/nishio/TypeScriptは型を再帰的に定義できない？) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.