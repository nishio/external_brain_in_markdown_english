---
title: "TypeScript Memo3"
---

ts

```typescript
  deselect(mouseState.target);
  if (handler !== null) {
    handler.onClick(event);
    handler = null;
    return;
  }
  
  ...
  
  const deselect = (x: PaperItem | null) => {
    if (x != null) {
      ...
    }
  }
```


ts

```typescript
  if (
    mouseState.type === "Nothing" ||
    mouseState.type === "Nothing_WithShift"
  ) {
    mouseState.handler.onClick(event);
    mouseState = INITIAL_STATE;
    return;
  }
  deselect(mouseState.target);

...

const deselect = (x: PaperItem) => {
  ...
}
```



---
This page is auto-translated from [/nishio/TypeScript Memo3](https://scrapbox.io/nishio/TypeScript Memo3) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.