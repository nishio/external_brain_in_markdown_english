---
title: "Recursively update the position of child elements of a group"
---

ts

```typescript
// Apply the position change diff to all children
const updatePosition = <T extends StateItem>(item: T, diff: paper.Point): T => {
  const newPosition = item.position.add(diff);
  if (isGroupStateItem(item)) {
    const newChildren = item.items.map((x) => (updatePosition(x, diff)))
    return {
      ...item,
      position: newPosition,
      nameplate: updatePosition(item.nameplate, diff),
      items: newChildren,
    }
  } else {
    return {
      ...item, position: newPosition
    }
  }
}
```


- [[Examples of generics needed]]

---
This page is auto-translated from [/nishio/グループの子要素の位置を再帰的に更新](https://scrapbox.io/nishio/グループの子要素の位置を再帰的に更新) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.