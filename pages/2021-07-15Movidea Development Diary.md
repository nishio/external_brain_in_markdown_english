---
title: "2021-07-15Movidea Development Diary"
---

Today's Picture of the Day
![image](https://gyazo.com/f9a4189bcd971734620945f7183cf949/thumb/1000)

---
Since only one dialog appears at a time, I'm thinking it's better to manage them by name rather than by individual boolean.
`type TDialog = "" | "AddFusen";`
ts

```typescript
const AddFusenDialog = () => {
  const [dialog, setDialog] = useGlobal("dialog");
  const open = dialog === "AddFusen";
  const onClose = () => {
    setDialog("");
  };

  return (
    <Dialog open={open} fullWidth={true} fullScreen={true} onClose={onClose}>
...
```


ts

```typescript
describe("dialog", () => {
  beforeEach(() => {
    cy.visit("/");
  });

  it("main", () => {
    cy.contains("Add Fusens").should("not.exist");
    cy.updateGlobal((g) => {
      g.dialog = "AddFusen";
    });
    cy.contains("Add Fusens").should("exist");
    cy.contains("Close").click();
    cy.contains("Add Fusens").should("not.exist");     
  });
});
```

![image](https://gyazo.com/6fa5fa28fab0b1e9e78a9b30fca053d6/thumb/1000)

By the way, do you want to use Fusen as the name to show to users or not?
- The previous implementation was Piece.
- Postit is a trademark of another company and I don't like it.
- StickyNote looks long and sticky when it's Sticky.
- Sticker would have a picture on it.
- I'm thinking of pushing through in Japanese.
- I think it would be better to use [[small stature]] as a word to express a new concept for Japanese people, away from the existing physical sticky notes.
- White background "whiteboard" sounds like writing with a pen, while "canvas" sounds like drawing a colorful picture.
    - This too could be a "place" for a change.
    - Kozane / Ba
        - The name of the application itself should be Kozaneba.

Strong will not to let the menu bar monopolize valuable screen space...
- ![image](https://gyazo.com/0a5cfb1157c2875f6c50634f86d5fc0f/thumb/1000)
    - Do you want more transparency or a darker background color?

menu
- Document
- [https://material-ui.com/components/menus/](https://material-ui.com/components/menus/)
- It depends on the local state of the component, but it's tricky when you bundle each menu button handler and such into a separate module.
    - Last time we created a "close when done" wrapper...
    - In the first place, is the menu one at a time as well as the dialog?
        - A child menu is possible.
            - In that case, there's no point in continuing to give the parents options, so why not still have one at a time?

Menus appear on sticky notes.
- But I don't like the subtlety of where it comes out.
- ![image](https://gyazo.com/c79a4a3216318e9d909e8e0205252f73/thumb/1000)

I didn't like it, so I fixed it.
- I feel this should be the default behavior.
- I can't specify where to show the menu, so I'm moving the invisible div to the mouse position.
- ![image](https://gyazo.com/a909ecdb82f6a283d68e3aceafb239c4/thumb/1000)


- After reading [[knee-swing (gymnastics)]] again, I realized that what I'm making is more like the Kozane method than the KJ method.
> KJ method... The KJ method is highly regarded as a method of "gathering the collective knowledge" of multiple people, and seems to be put to practical use by various companies. The Kozane method, which I have introduced here, is a closed-door intellectual production technique for a few individuals, and belongs to a relatively simple and elementary technique in Kawakita's system. In Kawakita's system, it is almost the same as what is called "KJ method B" writing.

drag/drop
- ![image](https://gyazo.com/b3f4995d67a2b56470437e07168cb5de/thumb/1000)
- I could drag and drop.
- [[HTML5 Drag&Drop API]]
- However, it moves the center to the drop position regardless of where you grabbed at the start of the drag, so you need to record the misalignment at the start and compensate for it.
- Maybe I should make a serious test of the conversion between the screen coordinate system and the world coordinate system once I make it...
    - I'm sure they'll use it in many places, not just this one.

I implemented a coordinate system transformation but it is difficult to test. The following does not work
test.ts

```typescript
cy.testid("2").should(
  "hasPosition",
  movidea.world_to_screen([top, left])
);
```


This is because the coordinate transformation is processed first at time T1. Even if we retry asynchronously later, it is meaningless because the "target value" has been calculated and fixed earlier.
test.ts

```typescript
cy.testid("2").should(
  "hasPosition",
  T1
);
```


To retry the coordinate calculation itself... I thought about it and put it in then.
test.ts

```typescript
cy.testid("2").then((el) => {
  return cy
    .wrap(el)
    .should("hasPosition", movidea.world_to_screen([top, left]));
```

This still doesn't work if the last state update is asynchronous, I had set the default asynchronous, but decided to make it default synchronous and only specify the option when asynchronous is needed, for some reason, all tests passed even with synchronous.

Postscript of the next day
- If you think about it, this is due to the fact that both screen drawing and coordinate transformation depend on the "current state", so it would have been better to have a pure function that explicitly passes all the necessary values for coordinate transformation.

When dragging by grabbing off-center, the second drag is inexplicably misaligned, or the center drag, which is supposed to return to the original position, does not return to the original position at all.
- I was wondering what was going on when I was testing a drag in Cypress, and I noticed some inexplicable misalignment. The coordinates must be off because the Cypress UI scrolls to display the object when it is dragged next...
- So, even in apps with overflow: hidden and wheel events preventDefault, Cypress scrolls to show the drag target, so I should have used pageX instead of clientX?
- That's not right... Even with that fix, the "inexplicable behavior" reproduces itself.
- For now, we know that it works as expected in the test case without overflow, so let's separate the behavior when it overflows as a description of the current behavior.
- I decided to let this case go through, because I operated the pattern of sticking out by hand and it worked as expected without any problem, so there is no problem in human use of the application I wrote, only that it behaves strangely when Cypress uses it.

Can now grab and drag off center.
- ![image](https://gyazo.com/f9a4189bcd971734620945f7183cf949/thumb/1000)
- The first time it strikes out, it's because the window wasn't in focus.


---
This page is auto-translated from [/nishio/2021-07-15Movidea開発日記](https://scrapbox.io/nishio/2021-07-15Movidea開発日記) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.