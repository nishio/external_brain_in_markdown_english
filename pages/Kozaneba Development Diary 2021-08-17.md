---
title: "Kozaneba Development Diary 2021-08-17"
---

prev  [[Kozaneba Development Diary 2021-08-16]]

![image](https://gyazo.com/d051980ddc2d3adbd02f96a93047d25c/thumb/1000)
---
Try [Kakau.app
- If you want more freedom, the Kozaneba way is better, but where do you feel Kakau is better?
- The one that comes up with the help button in the lower left corner is a keyboard shortcut, I think that's the clue.
- In other words, "highly flexible placement is achieved by the keyboard" instead of "highly flexible placement is achieved by the pointer.
    - They're supposed to focus on the parts that can be done with a keyboard.
- You're right, Kozaneba is useless without a pointer.
    - I'm thinking, "Of course you do."
    - Regroup thought "you know iPad+ApplePencil", but well, it wasn't that common yet.
    - Kozaneba also assumes "there is a touch screen capable of two-finger gestures."
    - However, different users have different devices, so I'd prefer to be able to customize how they're combined.
- If Kozaneba were to be used in an environment without a pointer?
    - Need a cursor, and two of them.
    - The added kozanes have an implicit order depending on the time of addition, so they can be selected by a one-dimensional cursor operation, which is the input cursor
    - There is an output cursor on the side to be placed, and the kozane selected by the input cursor is transferred to the output cursor position by key operation.
    - It's not a matter of reducing the degree of freedom, it's a matter of trying to increase the freedom and not making it more complicated and monstrous.
    - Implicit groups are created and added to them during keyboard operations
        - The default addition of an outline processor is like a tab delimiter.
        - A new group is created when "new group" which is equivalent to a new line is created.
    - The group selected by the cursor can be moved back and forth, folded, or joined to the end of the group in front of it.
    - This is, in essence, just a different way of displaying the outline processor.
    - It would be nice to be able to read a tree expressed in indentation depth from an outline processor (or Scrapbox) as a tree, that's what I need too!
- In other words, it is enough to "display the tree structure in group view" and "infer the tree structure from the arrangement of groups". The latter is easy to do, but hard to make it work without discomfort.

By the way, as for curly brace, it seems natural to introduce it in the form of "group frame decoration".

---
Continued from yesterday

> The context menu no longer appears.
- Wow. Okay.
- When div A follows mousemove, I want to detect that the mouse cursor is in div B below it.
- pointer-events: none; on div A at the timing of mousedown
- div A's mouseup event will also not be taken.
- I'm taking it with mousemove / mouseup of the parent div at the far end, so it's ok...
- was not.
- mouseup occurs before click, but if you change back to pointer-events: auto; in mouseup, you can't get click.

Just call onClick when you mouseup without mousemove.
- → Menu display position is set to event.currentTarget.
- Need to save the element at the time of mousedown.

ts

```typescript
let itemStore: {[id: string]: TItem};
let x = itemStore["foo"];  // can be undefined
```

Isn't it strange that x can be undefined and yet be of type TItem? Is there some option?
- There it is: [https://www.typescriptlang.org/ja/tsconfig#noUncheckedIndexedAccess](https://www.typescriptlang.org/ja/tsconfig#noUncheckedIndexedAccess)
- [thanks @tsukkee](https://twitter.com/tsukkee/status/1427492183351779329?s=20)

test
- Transition of how to make the initial state (e.g., two groups containing one kozane, etc.)
- T1: I first exposed setGlobal and used it to set the appropriate internal state
- T2: Next it is read from json in cy.fixture
ts

```typescript
cy.fixture("group_simple_json.json").then((json) => {
  cy.setGlobal(json);
});
```

- T3:
    - I don't think setGlobal can do everything too well to be exposed to users in production.
    - By creating an initial state with the API that will be exposed there, it also serves as a test of the API.
ts

```typescript
export const ready_two_groups = () => {
  cy.movidea((m) => {
    m.make_one_kozane({
      id: "1" as ItemId,
      text: "1",
      position: [-100, 0] as TWorldCoord,
    });
    m.make_items_into_new_group(["1"], { id: "G1", text: "G1" });
  });
  …
};
```

    - PS: I decided to put the utility functions in supports because this way the whole test case is imported when importing.
I have created a test file just to create the initial state.
- For example, "If you want to check the source code by human manipulation, you can open the file in Cypress and every time you edit the source code, the browser will be reloaded to its initial state, which is convenient.
    - Q: Why human operators?
    - A: Cypress tests describe "this is how it will behave when this event occurs on this element," but that does not necessarily mean that the event will occur when a human performs a natural operation
        - Like the "onClick does not occur" I mentioned earlier.
        - So when I'm making a modification that could break a place like that, I check it by hand and then I test that.
- When I was making and going through the tests by trial and error, the files were cluttered and divided.
    - ![image](https://gyazo.com/9560742400b55e9ae6f0ba238305afa8/thumb/1000)
    - It's because I added a test file saying, "Oh, I have to test this kind of operation from this initial state.
    - This can be written neatly with preparation and testing separated.
ts

```typescript
import { ready_one_kozane } from "./ready_one_kozane";
import { ready_two_groups } from "./ready_two_groups";

describe("drag", () => {
  beforeEach(() => {
    cy.visit("/#blank");
    cy.viewport(500, 500);
  });

  it("one kozane", () => {
    ready_one_kozane();
...
  it("two groups", () => {
    ready_two_groups();
...  
```


---
- The highlighting of nested groups doesn't seem to be working properly... the dragging itself seems to be working.
- I could fix the highlights and test the nested groups.
- Next, let's get the tutorial test running.
- The selection was still broken! A tutorial would be helpful to check out all the features in one place (yeah).
- Yay, all the tutorial tests passed!
- Surprisingly, the major operation of eliminating all Drag and Click event handlers and using the Mouse system for everything took less than two days.

![image](https://gyazo.com/83a671a840f1bc35f2c9b7036aca2f43/thumb/1000)
Oh, no, I thought I was done, but I forgot to comment out the "closed group" drawing.
- The tutorial doesn't say how to open and close the group yet.
- Fixed.

![image](https://gyazo.com/94f546504cc9900a068554c683f1648e/thumb/1000)
- Solves the problem of not being able to distinguish closed groups from untitled groups with only one kozane in them.

-----
functionality you want to add
- I want to be able to basically Cmd+Enter the OK-like button on the dialog.
- REPLACE button in the SPLIT dialog
- Create a user page and list of past saves
    - Warn me if I try to close a page I haven't saved?
- The "entire display of content at the point of opening" that was in the Regroup.
    - I had a kozane in an off-center place and said, "What? It's gone! and you're like, "Oh!
    - Spacebar to show the whole view
- Zoom to the center of the mouse cursor position
- Key bindings and display design can be changed on user pages
- Import from Keicho
- Import from Scrapbox
- Import indented bulleted text as a group
- Sharing with narrowed write permissions

The one I put on but not yet in the tutorial.
- Opening and Closing Groups
- Give the group a title
- Division of stickies
    - I can use it to duplicate and update.
    - I'd like to see it after Replace is on.

-----
- `"noUncheckedIndexedAccess": true,`
    - under
    - If the two-dimensional vector is `number[]`, there is a possibility that `v[0]` is undefined, so `[number, number]` is used.

And while we're at it.
- > [Twitter](https://twitter.com/nishio/status/1427279058128146435) I thought I could find out the bug of the mistake by separating vectors into "vectors of world coordinate system" and "vectors of screen coordinate system" and distinguishing them by type, but it turned out to be "the bug of converting the difference between two vectors of screen coordinate system (relative vector) into world coordinate system. I thought I could find a bug in which the difference between two vectors in the screen coordinate system (relative vector) is converted to the world coordinate system.
    - > In other words, we need 4 vector types: "world absolute", "world relative", "screen absolute", and "screen relative" (wait
- I actually tried this one (seriously?).
- For example, when a kozane in a group is dragged out of the group, its position changes by the amount of the group's position, but if the position of the object is an absolute coordinate, the absolute coordinates are added to each other.
    - This is because "the position of a kozane in a group is actually not an absolute coordinate but a relative coordinate from the position of the group", but then position becomes a relative or absolute type, and you cannot specify which one it is without looking at the parent.
- The other way is to assume that "the positions of objects that have no parent are relative coordinates from the origin. In this case, the positions of the objects are all relative coordinates, so adding or subtracting relative coordinates... adding the absolute coordinates `[0, 0]` to the result of the calculation gives the absolute coordinates...
    - If that's the case, there's no point in separating the types...
- Then the calculation of the center of gravity, a calculation that adds up the N absolute coordinates and divides by N to make it add up. This requires a type that depends on N...
- And well, that's how I got to the halfway point, but I thought that even if I went through with this, it wouldn't be very effective in avoiding bugs for the increased costs in the future, so I decided to stop.
- If you want to tweak the value side, just extend `[x, y]` to `[x, y, 1]`. If you take the difference, the third becomes 0 and becomes a relative vector, and adding N and dividing by N can be verified by the fact that the third returns to 1. In the end, any method just adds `[0, 0, 1]` at the end, so there is no merit in making it more complicated.

---
- ✅Magnification centered on mouse cursor position
    - ![image](https://gyazo.com/d051980ddc2d3adbd02f96a93047d25c/thumb/1000)


I was thinking about this when I saw [/forum-jp/about this site](https://scrapbox.io/forum-jp/about this site), but I'm not sure if it's a good idea to make it a "request to Kozaneba" or not.
- If the projects are "better grouped together without subdivisions" and "differentiated by members", then I feel like there should be one group where you can put an invite link and anyone can enter.
- If it's going to be one, why not include not only Kozaneba, but Keicho and "The Intellectual Production of Engineers" as well?
- But then the title of the project would be something like "Request to Nishio", which is odd.
- To be more precise, it could be "Nishio's requests for intellectual productivity writings and software", but that's a long story.
- To begin with, "request" is a strong word.
    - But by saying "this is a good place to write your requests," it may have created an incentive for people with requests to write them.
    - Some people don't write "Let's discuss."
    - On the other hand, some people might write a long story about their own theory.

next  [[Kozaneba Development Diary 2021-08-18]]

---
This page is auto-translated from [/nishio/Kozaneba開発日記2021-08-17](https://scrapbox.io/nishio/Kozaneba開発日記2021-08-17) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.