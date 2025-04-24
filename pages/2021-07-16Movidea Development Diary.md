---
title: "2021-07-16Movidea Development Diary"
---

Recently Movidea's development is diary style like this page, but the reason why they don't do it like [[pRegroup]] or [[pKeicho]] is a feeling like "the structure may occur after the fact".

In fact, I went back to my diary and said, "Oh, I thought I made a list of functions to implement," and then I thought, "This paragraph, if I'm going to refer to it over and over, I should cut it out on a separate page and have a non-date title," and [[MovideaFunctionality required to make it actually usable]] page was created.

I wonder if they're trying to write it out first with no cost, because Cypress's trial and error and feature additions are all over the place, and there's extra cognitive cost in separating them into pages.

There are a lot of meeting interrupts today, and we'll focus on looking back, etc.

The drag function I created yesterday uses [[HTML5 Drag&Drop API]], which was a first for me, so I have a lot to write about, but I haven't written it yet.
- Drag Target
    - Make it draggable
    - Record how far off-center the mouse down position is at the start of the drag
tsx

```
<GroupDiv ... onDragStart={onDragStart} draggable={true}>
```

ts

```typescript
const onDragStart = (event: React.DragEvent<HTMLDivElement>) => {
  updateGlobal((g) => {
    const [x, y] = value.position;
    const [cx, cy] = screen_to_world([event.clientX, event.clientY]);
    g.dragstart_position = [cx - x, cy - y];
    g.drag_target = value.id;
  });
};
```

- drop target
    - PreventDefault with onDragOver is a condition for drop acceptance.
ts

```typescript
<div id="canvas" onDrop={onDrop} onDragOver={allowDrop}>
```

ts

```typescript
export const allowDrop = (event: React.DragEvent<HTMLDivElement>) => {
  event.preventDefault();
};
export const onDrop = (event: React.DragEvent<HTMLDivElement>) => {
  updateGlobal((g) => {
    const [dsx, dsy] = g.dragstart_position;
    const [x, y] = screen_to_world([event.clientX, event.clientY]);
    g.itemStore[g.drag_target].position = [x - dsx, y - dsy];
  });
  event.preventDefault();
};
```


Fixed to not display plus sign when dragging
- When testing with Cypress, `event.dataTransfer` is undefined in `onDragStart`, so I needed to ignore it when not present.
ts

```typescript
  const onDragStart = (event: React.DragEvent<HTMLDivElement>) => {
    if (event.dataTransfer !== undefined) {
      event.dataTransfer.effectAllowed = "move";
    }...
```

ts

```typescript
export const allowDrop = (event: React.DragEvent<HTMLDivElement>) => {
  event.dataTransfer.dropEffect = "move";
  event.preventDefault();
};
```



- [Try anything you're unsure about as soon as possible.
On the other hand, as for the cloud saving feature, which I tried earlier because I was worried about it in the last Regroup, I'm going to put it off this time.

This week's summary
    - [[Update with immer and test with Cypress]]
    - [[TypeScripting Cypress]]
    - [[2021-07-13Movidea Development Diary]]
    - [[2021-07-14Movidea Development Diary]]
    - [[2021-07-15Movidea Development Diary]]

Representation of a rectangular range by the DOM
Intersection judgment with rectangular range
- Whether to select by partial intersection or whole inclusion
    - Do you allow some of the group to choose?
        - An image that does not allow


---
This page is auto-translated from [/nishio/2021-07-16Movidea開発日記](https://scrapbox.io/nishio/2021-07-16Movidea開発日記) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.