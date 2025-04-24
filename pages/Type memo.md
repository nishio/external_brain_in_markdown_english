---
title: "Type memo"
---

It's not enough to have a mold.
ts

```typescript
const makeV = (f: boolean) => {
  if (f) {
    return { x: 1, y: 1 };
  } else {
    return {};
  }
};

const v = makeV(true);
const x = v.x; // x: number | undefined
```


Because it was received as any, an unnamed, half-formed object is being passed through (the variable name "x" is also a bit of a mess).
ts

```typescript
type FIXME = {
  nameplate: number | null;
  isOpen: boolean;
};

export const createNewGroupStateItem = (
  position: paper.Point,
  items: number[] | StateItem[],
  x: FIXME,
): GroupStateItem => {
  return createGroupStateItem(position, items, x, createUniqueID());
};

export const createGroupStateItem = (
  position: paper.Point,
  items: number[] | StateItem[],
  x: FIXME,
  id: ItemID,
): GroupStateItem => { ... 
```



ts

```typescript
import { ToolEvent } from "paper";
export const isTwoFingerGesture = (event: ToolEvent) => {
  const e: any = (event as any).event;
```



ts

```typescript
export const convertStateItemToFirestore = (x: StateItem) => {
  const ret: any;
  ret.type = x.type;
  ret.id = x.id;
  ret.position = [x.position.x, x.position.y]
  if (isPieceStateItem(x)) {
    ret.text = x.text;
	...	
  } else if (isPathStateItem(x)) {
    ret.opacity = x.opacity ?? 1.0;
	...
  }
  return ret;
```


ts

```typescript
export const createBlankFirestore = (): FIRESTORE_DOC => {
  const ret: any = {
    version: 2,
  };
  ret.itemStore = {};
  ret.drawOrder = [];
  return ret;
};
```

ts

```typescript
export const createBlankFirestore = (): FIRESTORE_DOC => {
  const version = 2;
  const itemStore = {};
  const drawOrder: ItemID[] = [];
  return { version, itemStore, drawOrder };
};
```


ts

```typescript
export const onOverlayCanvas = (f: (...args: any[]) => unknown) => {
  return (...args: unknown[]) => {
    paper.projects[1].activate();
    const ret = f(...args);
    paper.projects[0].activate();
    return ret;
  };
};
```

ts

```typescript
import { ToolEvent } from "paper";

export const onOverlayCanvas = <T extends [ToolEvent] | []>(
  f: (...args: T) => unknown,
) => {
  return (...args: T) => {
    paper.projects[1].activate();
    const ret = f(...args);
    paper.projects[0].activate();
    return ret;
  };
};
```



---
This page is auto-translated from [/nishio/Type memo](https://scrapbox.io/nishio/Type memo) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.