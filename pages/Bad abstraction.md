---
title: "Bad abstraction"
---

I did it once for the best of intentions, but now I think it was a bad design.
ts

```typescript
  if (
    state.type === "MouseDownOnNothing" ||
    state.type === "MouseDownOnNothing_WithShift" ||
    state.type === "LassoMouseDownOnNothing" ||
    state.type === "LassoMouseDownOnSelection"
  ) {
    state.handler.onDragEnd(event, dragStartPoint);
    state = INITIAL_STATE;
    return;
  }
```


I can't follow in the IDE what exactly `state.handler.onDragEnd` refers to, it jumps to the following

ts

```typescript
export type Handler = {
  onDrag: (event: ToolEvent, dragStartPoint: paper.Point) => void;
  onDragEnd: (event: ToolEvent, dragStartPoint: paper.Point) => void;
  onClick: (event: ToolEvent) => void;
};
```


So, when `state.type === "LassoMouseDownOnNothing"`, you will have to follow what exactly the value of `state.handler.onDragEnd` is by yourself without relying on the IDE.

ts

```typescript
  if (global.selectedTool === "lasso" && leafItem === null) {
    // Start new selection
    clearLasso();
    hideBalloon();
    state = {
      type: "LassoMouseDownOnNothing",
      handler: startLasso(),
    };
    return;
  }
```


So I ended up having to read the implementation of `startLasso()`, and when I read it, I see that this handler has no state, so it is simply one function being called.

I wonder if there was any benefit to such an abstraction, which is lumped together because the abstract operation of "calling dragEnd" is the same in four different states, but there was no need for it.

---
This page is auto-translated from [/nishio/良くない抽象化](https://scrapbox.io/nishio/良くない抽象化) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.