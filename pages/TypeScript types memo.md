---
title: "TypeScript types memo"
---

- [[TypeScript types]]

- `T1 extends T2 ? F<T1> : never`
    - similar to `f(t1 as T2)`
- circularly references
    - `{0: T1}[T extends any ? 0 : 0]`
    - `{0: T1, 1: T2}[CONDITION ? 0 : 1]`
        - `CONDITION ? T1 : T2`

ts

```typescript
// type GET_LAST<X extends LIST> = 
//   X extends [BIN, LIST] ? CAR<X> : GET_LAST<CDR<X>>
// NG: Type alias 'GET_LAST' circularly references itself.

type GET_LAST<X extends LIST> = { 
  0: CAR<X>, 
  1: GET_LAST<CDR<X>> 
}[X extends [BIN, LIST] ? 0 : 1]
// OK
```

- CONDITION
    - `N extends any`
        - true
        - `any extends any` does not work
    - true: any, false: never
        - `N extends M ? ... : ... Can only be used in the form `.

---
This page is auto-translated from [/nishio/TypeScript types memo](https://scrapbox.io/nishio/TypeScript types memo) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.