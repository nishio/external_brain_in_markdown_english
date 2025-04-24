---
title: "Bundle state names and variables and constrain by type"
---

- [[TypeScript types]]
ts

```typescript
type STATE_TYPE = "INITIAL" | "HAS_NUMBER";
let state: STATE_TYPE = "INITIAL";
let value: number | undefined;
const setNumber = (x: number) => {
  state = "HAS_NUMBER";
  value = x;
}
const useNumber = () => {
  if (state === "HAS_NUMBER") {
    const x: number = value;  // NG
    // Type 'number | undefined' is not assignable to type 'number'.
  }
} 
```


ts

```typescript
const useNumber = () => {
  if (state === "HAS_NUMBER") {
    if (value !== undefined) {  // mmm...
      const x: number = value;  // OK
    }
  }
}
```


ts

```typescript
type STATE_TYPE = (
  { type: "INITIAL", value: undefined } |
  { type: "HAS_NUMBER", value: number }
);
let state: STATE_TYPE = { type: "INITIAL", value: undefined };
const setNumber = (x: number) => {
  state = { type: "HAS_NUMBER", value: x };
}
const useNumber = () => {
  if (state.type === "HAS_NUMBER") {
    const x: number = state.value;  // OK
  }
}
```


`console.log(state)` become more useful

---
This page is auto-translated from [/nishio/状態名と変数を束ねて型で制約](https://scrapbox.io/nishio/状態名と変数を束ねて型で制約) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.