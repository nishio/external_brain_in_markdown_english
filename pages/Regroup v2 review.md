---
title: "Regroup v2 review"
---

Assuming that the current Regroup code is to be discarded and rebuilt, a look back is needed before rebuilding.
K: The good part
P: Problems, what didn't work
T: Next Action

P: Did not write the test from the beginning
- It was a project that was difficult to test because it was difficult to write tests in GUI, and because it used Canvas, DOM emulation did not work, but the lack of testing made it easier to break the project from a certain scale.
- I started testing with [[jest-electron]] after it became too fragile, but the difficulty increased because I started testing after it became too complicated.

P: I've required Paper.js
- I didn't have enough understanding of the module system because I was using TypeScript for the first time in earnest, and this way of doing things was PAPER was ANY
    - [[I spent two days eradicating ANY.]] It was discovered in
- If you're going to rebuild, do it from the beginning in the style of "allow no more than a very localized version of any".

P: I used ToolEvent in paper.js
- This is a framework that assumes that the handling of mouse events is neatly switched by the global state of "tool".
    - Realistically, it isn't.
    - Especially on the iPad, multi-touch gestures are handled in a separate and independent event handler, which has become a source of troublesome problems.
    - For example, if a hand inadvertently touches the screen while writing with a pen, multi-touch occurs. How to deal with such a situation?

Undo Design
- From very early on, we thought that Undo should be there.
- Therefore, we designed React's state update hooks to manage Undo/Redo.
- If you move one sticky, it will update its status and the Undo list will grow.
- This didn't work.
    - When there are more functions to move multiple stickies at once, reusing a function to move one sticky at a time would result in Undo for each sticky.
    - Multiple piece moves are tied together to update the state at one time.
    - When stickies and paths are created, if you select them and move them around...complication!
    - I tried to change it later to a form that explicitly takes snapshuts, but it breaks all over the place.
- Undo broke and I used it in that state for a while, but there are not many cases where Undo is needed.
    - I misspelled it with a pen and want to put it back.
    - I want to put it back because I put it down in a weird place on a multi-piece move.
- If you miss moving one sticky, you usually just move it further.
    - Undo of one sticky note was a "feature that customers did not ask for".

About Network Synchronization
- Casual Synchronization with Firestore
- You can edit it as long as you are looking at the same URL.
    - A convenient system that can be fiddled with on a PC, smartphone, or tablet for a single person's use.
        - Can be shared via Handoff or AirDrop.
    - But basically, it's overwritten with the information that arrived at the server, so it's easily broken if multiple people edit it at the same time.
- Users may not want to edit in the first place
    - I'm afraid of accidentally breaking it."
    - If you make an "edit request" in the default non-editing mode, and the person who has editing rights now passes it on, there should always be one editor.
    - The mere viewer was also supposed to open and close the bundled sticky notes.
    - Isn't Regroup's map basically for others to see in the first place?
        - Does this mean that the "thought process" is not in an appropriate form to show to others as it is, and that we have to do one more step?
        - Not sure if that "clean-up" process should be able to be done on Regroup.
        - There's also the theory that they're not going to do the "let's get a clean copy and show it to you" thing anyway.

Every time I update it, I erase the canvas and redraw it.
- Would it be faster if I only update what has changed? This should be verified.

On the iPad, I'm converting to an image and zooming, on the PC, I'm changing the zoom on the wheel event.
- Due to the wheel event not having an "end event" unlike a swipe.
- This would be a rather large effect of the drawing delay.

Need a pen?
- Hmmm, not essential, but it is beneficial to be able to easily add things that are difficult to express with just the placement of stickies
- Was it right to make the entire surface Canvas with pen input as the basic premise?
    - This is slightly iffy.
    - When used as a normal handwritten note application...
        - It's indeed a browser app, so the behavior is heavy.
        - It's not explicitly stated, but Firestore's stuck on the document space limit.
    - You could make the stickies as DOM, and only the handwritten lines could be Canvas or SVG for each group.
        - Advantages of this method:.
            - Maybe you can find the sticky using your browser's standard search.
            - Reduces "difficult to test because of Canvas" problems
            - Can you let React handle the diff updates?
- Full canvas is needed for lasso selection, etc.


- [[Should we rebuild or not?" is a false choice.]]

---
This page is auto-translated from [/nishio/Regroup v2振り返り](https://scrapbox.io/nishio/Regroup v2振り返り) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.