---
title: "2021-07-27Movidea Development Diary"
---

![image](https://gyazo.com/eef32a81fb1ce4968435b142ea186569/thumb/1000)
It is now possible to move in and out of groups, which was previously too difficult!
The stacking order is perfect, with the last one moved on top.
The lesson learned is that it's too hard to update the tree with React's "don't do destructive updates bind", so let's use [[immer]] to free ourselves from the bind.

After this, I fixed the group's background not being translucent.
I also found that it can drop on itself, so I added a process to avoid inconsistencies.

What happens if I drop a selection into a group?
- Thought it would be a good idea to add each sticky to a group.
- The display is wrong after adding, for some reason.
- Only top-level elements are selected" is incompatible with "the selection is not deselected after moving the selection".
    - Both stickies in a group and stickies in a selection are drawn.
- Deselected when dropped into a group.
    - At first glance, it seems natural, but won't the user be caught in this inconsistency?
    - This operation is difficult to redo, so you'll need to be able to Undo

Add to the diagram
- ![image](https://gyazo.com/6a0a42a36fde5cddbfedf72d05c6b487/thumb/1000)
- I was just going to do C.
- A Bug
    - DragDropAPI can also drop to itself.
    - If a group can be dragged and a group can be a drop target, then of course there can be a "drop on itself", which is a problem!
    - So when there is a drop to itself, it transfers the process to a drop to canvas.
- B Specifications
    - Dragging a selection to a group will deselect it, unlike other cases

Testing in and out of groups
![image](https://gyazo.com/e0c8f415236881280aba892e04de5033/thumb/1000)

Tried the "if there's a group within a group" thing and found a nasty problem.
- The element being dragged is displayed in full size even when zoomed out...
- ![image](https://gyazo.com/7db474bb252d1697f0830a570bc63610/thumb/1000)
- I tried cloneNode and `event.dataTransfer.setDragImage` but transform: scale seems to have no effect
- This is browser implementation-dependent behavior not specified in the specification
    - Firefox was fixed 5 months ago, but I'm not sure if Chrome has been fixed yet.
    - [941356 - drag image not correctly created when parent has css transform](https://bugzilla.mozilla.org/show_bug.cgi?id=941356)
- Wife: "It may not be optimal, but it's not so much that it's seriously damaging to what we want to achieve with this program as that it may be convenient to check the magnified view by pressing and holding the mouse without zooming.
    - Well... let's hold off for now then.

Aside from that, it's rather buggy to begin with.
- The bounding box when there's a title is a little off, too.
- Fixed.
    - ![image](https://gyazo.com/9f2fb2546b2e6feb0d79d935bf6c4461/thumb/1000)
    - I saw this result with the naked eye and thought it looked misaligned, but it just feels that way because of the menu bar and the group titles, and the stickies are centered.
        - I wrote the coordinate values in the test case and checked them.
- ![image](https://gyazo.com/1aebfcfa006e28f8a2dbd915a86be17e/thumb/1000)

Your bounding box is out of alignment by the amount of FUSEN_BORDER.
- ![image](https://gyazo.com/56c895d33935467414840489cad708d0/thumb/1000)
- fixed

What to do next
- Add a sticky when you press the button in the Add Sticky dialog.


---
This page is auto-translated from [/nishio/2021-07-27Movidea開発日記](https://scrapbox.io/nishio/2021-07-27Movidea開発日記) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.