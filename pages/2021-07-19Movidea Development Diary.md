---
title: "2021-07-19Movidea Development Diary"
---

prev  [[2021-07-16Movidea Development Diary]]
![image](https://gyazo.com/7f992e21a62701c5b74dbb7f46e5914e/thumb/1000)
---

[[pMovidea]] made.
    - I just wrote this in [[2021-07-16Movidea Development Diary]].
    - > I have a feeling that Movidea's recent development is diary style like this page, but not like pRegroup or pKeicho, because "the structure may be generated after the fact".
- Because when the week opened up and I wanted to continue, it took me a while to find the last page.
    - By the end of the week, what I wrote over the weekend will have sunk in.
    - I'm going to write something on pMovidea over the weekend that I thought "I'll do this next week".

> In the principle of trying something that makes you uneasy as soon as possible, next time you should try to select a range of items against the DOM.
- I'll do this.
- Representation of a rectangular range by the DOM
    - Creating a div by dragging start in canvas
        - How to organize the mouse event, it was chaotic last time too.
        - There's already a group drag that's split into separate files at the start and end, and that's not good.
        - For now, it's all in one.
    - Should it be a single state transition diagram?
- Intersection judgment with rectangular range
    - Whether to select by partial intersection or whole inclusion
        - Do you allow some of the group to choose?
            - An image that does not allow


![image](https://gyazo.com/6a6e4e44896ffa94875026803d31033a/thumb/1000)
- Maybe it's better not to BORDER?

![image](https://gyazo.com/98018d5b2d2252fc48a31e5bdb3d21f4/thumb/1000)
It seems useless to recalculate the bounding box when there is no content update, but caching the bounding box value and recalculating it appropriately is also "introducing an extra state", so we should first calculate it naively and cover it with a test, then measure it and cache it only if it is slow. I think we should put in a system to cache only if it is slow.

I was able to do it.

Create test cases
- Place about 9 sticky notes and select

![image](https://gyazo.com/7f992e21a62701c5b74dbb7f46e5914e/thumb/1000)

test.ts

```typescript
cy.get("#canvas").trigger("mousedown", 150, 150);
cy.get("#canvas").trigger("mouseup", 450, 450);
cy.movidea((m) => {
  cy.wrap(m.getGlobal().selected_items).should("to.deep.equal", [
    "0,0",
    "0,1",
    "1,0",
    "1,1",
  ]);
});

cy.get("#canvas").trigger("mousedown", 250, 250);
cy.get("#canvas").trigger("mouseup", 150, 150);
cy.movidea((m) => {
  cy.wrap(m.getGlobal().selected_items).should("to.deep.equal", ["0,0"]);
});
```


Can we make a custom command to `cy.movidea((m) => {cy.wrap(m.getGlobal().selected_items).should("to.deep.equal"`?
- No, but extending assertions on your own is a pain because you have to write them in Chai.
- Anyway, I checked [Chai's documentation](https://www.chaijs.com/api/bdd/#method_eql) and it looks like `to.deep.equal` should be `to.eql`.

index.ts

```typescript
Cypress.Commands.add("getGlobal", (callback: (g: State) => unknown) => {
  return cy.movidea((movidea) => {
    return cy.wrap(callback(movidea.getGlobal()));
  });
});
```

test.ts

```typescript
cy.get("#canvas").trigger("mousedown", 250, 250);
cy.get("#canvas").trigger("mouseup", 150, 150);
cy.getGlobal((g) => g.selected_items).should("to.eql", ["0,0"]);
```

Well, I guess that's about it.



Can you move the selection?
- A single drag move used the DragDrop API, but this time there are multiple
    - Putting it in one DIV?
        - And there's a selection DIV.
    - Do we use for to update the position of each ID?
        - subtle

Put the DOM of the selected item in the selection div at the time of either mouse down in the selection or the completion of the selection.



---
This page is auto-translated from [/nishio/2021-07-19Movidea開発日記](https://scrapbox.io/nishio/2021-07-19Movidea開発日記) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.