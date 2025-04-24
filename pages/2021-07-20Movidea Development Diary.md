---
title: "2021-07-20Movidea Development Diary"
---

prev  [[2021-07-19Movidea Development Diary]]
![image](https://gyazo.com/f8bac0032f9b9fc356ffc5b1c9a95184/thumb/1000)

---
The problem around the mouse event, the last time I did Regroup, I was not able to understand it properly because I became aware of it after it became quite complicated, but this time I was able to understand it.

![image](https://gyazo.com/eff9b3ce1c710834d545360b4c3fecd3/thumb/1000)
The preferred, natural, "meaning chunk" for humans is the one on the left.
- Moving groups by dragging
- range selection
- Moving a selection by dragging

In reality, however, the browser specifications
- The drop event of a drag move is the same in both cases
- mousemove and mouseup are called no matter which operation is being performed.

At the time of Regroup, everything started mousedown, partly because everything was operated on the Canvas element.
- ![image](https://gyazo.com/85789af4ab3dcdc611e2080af074c7cb/thumb/1000)
- The crossed-out mark means "processing performed when mouseup occurs without mousemove after mousedown".
    - In short, click

Therefore, these
- Group a "lump of processes" into a handler object to determine which handler to use at the timing of mousedown.
- ![image](https://gyazo.com/c7c5e860137e7dc2d7aa033be8fca133/thumb/1000)

Looks good at first glance, but no.
- There is processing that must be done in common by multiple handlers.
    - If I write in each one, there will be an omission.
    - To solve this problem, a design change was made to "put another layer between the layers and perform common processing all together.
- It was implicitly assumed that the process would be finalized at the mousedown stage.
    - Cases that didn't were harder to handle.
        - What if another mousedown comes right after the mousedown and it's multi-touch?
        - Drop a sticky into a group by dropping it into the group" is divided into cases depending on the situation at the time of drop.

With that in mind, how do we sort this situation out this time around?
- ![image](https://gyazo.com/eff9b3ce1c710834d545360b4c3fecd3/thumb/1000)
- I thought I had it figured out, but then I lost it again...
- I thought that since the state was implicitly occurring, it would be a good idea to manage it yang!
- The current code is flagging isDragging on mousedown.
- No, no, the current implementation already shows a difference between the right diagram I wrote in "my understanding" and the actual behavior.
    - mouseDown, mouseMove, dragStart, drop are executed in this order
    - As a result, the flag remains up.
    - Actual behavior
        - ![image](https://gyazo.com/7f89d3da0b90f44e7fc1710c725600a8/thumb/1000)
    - In this case, the element at the start of the upper process is DOMically contained in the element of the lower process, so there is a way to add mousedown to the upper process, grab it there, and stopPropagate.
        - I mean, there doesn't seem to be any other way to do it.
        - In short, just as source code has a lexical scope based on its inclusion in the code, the DOM has a scope based on its inclusion.
        - So, if you think about it, flagging with mousedown and doing a specific process with mousemove only when the flag is up is cutting off a section on the time axis with a dynamic scope.
    - A graphical representation of it would look like this
        - ![image](https://gyazo.com/3452e6e3fc8f0ba0929872154279528c/thumb/1000)
    - Based on this, here's what we need to do this time
        - ![image](https://gyazo.com/0c46bca6d85909389dd36c513b665706/thumb/1000)
        - This time it's still simple enough that we could design it, but if we get a couple more cases of this, we won't be able to draw it on the diagram.

What to do this time in light of this
- I don't rush to add weird layers.
- No rushing to divide

Implement "Move Selection" and "Move Stickies Out of Group" and write a test case before refactoring.

---

2021-07-21
What I noticed after a night's sleep
- If you want to transfer the elements of the selection at the time of selection
- After a selection is made, clicking outside the selection must be undone
- So there's another state of affairs occurring here.

Condition should be subject to testing

Now the local variable has state, but make it global
before
ts

```typescript
let isDragging = false;
export const onMouseDown = (...) => {
  isDragging = true;
  ...
};
export const onMouseMove = (...) => {
  if (isDragging) {
    ...
  }
};
export const onMouseUp = (...) => {
  if (isDragging) {
    ...
    isDragging = false;
  }
};
```


after
ts

```typescript
export const onMouseDown = (...) => {
  updateGlobal((g) => {
    ...
    g.mouseState = "selecting";
  });
};
export const onMouseMove = (...) => {
  const g = getGlobal();
  if (g.mouseState === "selecting") {
    ...
  }
};
export const onMouseUp = (...) => {
  const g = getGlobal();
  if (g.mouseState === "selecting") {
    updateGlobal((g) => {
      ...
      g.mouseState = "selecting";  // intentional bug, should be ""
    });
  }
};
```


test
test.ts

```typescript
    cy.get("#canvas").trigger("mousedown", 50, 100);
    cy.getGlobal((g) => g.mouseState).should("to.eql", "selecting");
    cy.get("#canvas").trigger("mouseup", 300, 400);
    cy.getGlobal((g) => g.mouseState).should("to.eql", "");  // intentional fail
```


Now we can detect when we're in a strange state.
- Deliberate bugs were fixed only after testing was done to make sure they would rub properly.

Yesterday's "I didn't realize that mousedown comes before dragstart" was verified with a test case.
test.ts

```typescript
    cy.testid("1").trigger("dragstart", "center");
    cy.getGlobal((g) => g.mouseState).should("to.eql", "");
    cy.get("#canvas").trigger("drop", 250, 250);
```

I thought this would fail, but it doesn't. I see.
- Mousedown occurs first when humans operate.
- In the test case, I'm just issuing the dragstart event, so no mousedown occurs.

If you test this as if it were a real event, it would look like this
test.ts

```typescript
  it("is not selecting", () => {
    cy.testid("1").trigger("mousedown", "center");
    cy.testid("1").trigger("mousemove", "center");
    cy.testid("1").trigger("dragstart", "center");
    cy.getGlobal((g) => g.mouseState).should("to.eql", "");
    cy.get("#canvas").trigger("drop", 250, 250);
  });
```

This fails as expected.
And then stopPropagation and confirm that it works as expecteddone

So far, so good. Next, we'll discuss the "post-selection" condition I noticed this morning.
- Selection should not be released by dragging
- Should be canceled on mousedown outside the selection
- If you dare to draw a diagram, it looks like this
- ![image](https://gyazo.com/651a16356375b1045fad41bffd6b5827/thumb/1000)
- 🤔
- ![image](https://gyazo.com/57c3b688037db501edbe090f08bd39d6/thumb/1000)
    - I can write the release code in A.
    - But I'm afraid I'll leave it out when more similar ones come along in the future.
    - You can't automatically put a release code on all of them.
        - Because you can't unlock it with a B.
    - In natural language, "mousedown outside the selection to release".
        - What is this "except"?
            - What about mousedown on a sticky that is DOM-included in the selection?
            - This is "DOM stacking order" (oops, another new scope)
            - The selection is before the selected stickies (most of them) in the stacking order of the DOM, so it should block the event.
            - ![image](https://gyazo.com/f77daf0dca10987a865497d17abc7775/thumb/1000)
                - Clicking C does not cause mousedown on stickies
                - D is a click outside the selection, so you can deselect it.
            - Wait, so when you do the "add selected to div" thing, you need another div?
                - Can I use z-index?
            - No, it's not. There's no need to use a div to visualize the selection to summarize the selection.

Decided to highlight the selected ones by lowering the opacity of the "not selected ones."
- ![image](https://gyazo.com/954963b304cfd7aff577f27a97efc3f2/thumb/1000)
- This still doesn't implement state deactivation.

Oh, no, if dragging the "Show Selection" and the div that wraps the selected object are separated, then dragging the "Show Selection" won't move the selected object...

I was able to get to the point where I could select multiple items and drag them around, but the "Show Selection" is not moving.
- ![image](https://gyazo.com/91dae056758bbe6355c7754dd1f24c47/thumb/1000)

It's done.
- ![image](https://gyazo.com/f8bac0032f9b9fc356ffc5b1c9a95184/thumb/1000)

After writing the test case, it became clear that the position was off by only 2 pixels vertically from the expected position.
- Dragstart the (0, 2) of the div with top:150px and the event that actually occurs is (150, 150)
- Seems to be reproduced only in the Cypress environment...
test.ts

```typescript
    cy.getGlobal((g) => g.selected_items).should("to.eql", items);
    cy.getGlobal((g) => items.map((id) => g.itemStore[id].position)).should(
      "to.eql",
      [
        [0, 0],
        [0, 200],
        [200, 0],
        [200, 200],
      ]
    );
    cy.get("#selection-view").trigger("dragstart", 0, 2); // misterious 2px
    cy.get("#canvas").trigger("drop", 100, 100);
    cy.getGlobal((g) => items.map((id) => g.itemStore[id].position)).should(
      "to.eql",
      [
        [-50, -50],
        [-50, 150],
        [150, -50],
        [150, 150],
      ]
    );
```



---
This page is auto-translated from [/nishio/2021-07-20Movidea開発日記](https://scrapbox.io/nishio/2021-07-20Movidea開発日記) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.