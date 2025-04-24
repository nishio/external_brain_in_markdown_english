---
title: "TypeScript Memo"
---

ts

```typescript
let state: ({ type: "INITIAL", value: null } | { type: "WITH_NUMBER", value: number })
const f = () => {
  if (state.type === "WITH_NUMBER") {
    let x: number = state.value;
  }
}
const f2 = () => {
  const type = state.type;
  if (type === "WITH_NUMBER") {
    // let x: number = state.value;  // NG
    // Type 'number | null' is not assignable to type 'number'.
  }
}
```


ts

```typescript
// before
if (dragStartType === "RootPiece") {
  if (target !== null && isPiecePaperItem(target)) {
    updatePiecePosition(target);
    deselect(target);
  } else {
    throw new Error("never");
  }
}
//after
if (mouseState.type === "RootPiece") {
  updatePiecePosition(mouseState.target);
  deselect(mouseState.target);
}
```


---
This page is auto-translated from [/nishio/TypeScript Memo](https://scrapbox.io/nishio/TypeScript Memo) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.