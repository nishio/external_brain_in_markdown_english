---
title: "2021-07-28Movidea Development Diary"
---

![image](https://gyazo.com/320c2e22ced1b194afefcac330dbfe5e/thumb/1000)

-----
prev  [[2021-07-27Movidea Development Diary]]

![image](https://gyazo.com/87104146ebd00da1ccd57eed6e6f5fb6/thumb/1000)
- I was able to add the sticky itself.
    - ![image](https://gyazo.com/d77ac841a28546cda472020aba02b763/thumb/1000)
    - ![image](https://gyazo.com/6707d7e7fc3f909a38257de374aade3e/thumb/1000)
    - Oh well, I guess the border will be outside the WIDTH of the div...
    - It's not hard to fix, but that's not such a high priority, so we'll see later.

Unlike the previous Regroup, stickies are now added in groups instead of individually.
- So, "Oh my gosh, it's covered where I already put stuff!" no longer happens.
- Do I place them in a way that avoids what's already there?" but it's still a hassle if they are scattered and placed in the gaps between the already placed ones.
- Should I leave it selected? I thought about it, but one click would deselect it.
- So the conclusion that it would be appropriate to group
- You can move it anywhere you want and then ungroup it, or in this version, you can "drag it out of the group" so you can drag out only what you need and delete the rest all together.

I'd like it to always be in the center of the screen no matter where I'm scrolling.

Other necessary functions
- ungrouping
    - Context menu for groups
- grouping
    - Context menu for selections
- deletion
    - Context menu for stickies and groups
Context menus everywhere.

About Tutorials
- I'm currently working on the add sticky dialog first, but that doesn't make any sense for the quirks.
- I thought about a dedicated tutorial dialog, but I think it would be better to create a page for tutorials in the tutorial section.
- Tutorials can be done without cloud storage in the first place.

---

Selections can now be grouped and regrouped.
- I don't like the way you behave a little.
- After making a selection, a menu appears and you can no longer drag a selection without one click to close that menu.
    - Should I make a selection and then click on the selection to bring up the menu?
    - It was more natural to click on the selection to bring up the menu.

![image](https://gyazo.com/320c2e22ced1b194afefcac330dbfe5e/thumb/1000)

Today's Summary
- Adding Sticky Notes
- Ungrouping and deleting groups
- Deleting Stickies
- Group selected items and delete them all together

Try it out
![image](https://gyazo.com/bdb657eb2680417be8ec0422a93c18c3/thumb/1000)

Hmm, it's weird to have a sticky in full size while dragging because you don't know where it's going to be dropped until you drop it.
Will I ever get used to it?

- [[Is the next development a network connection or a solution to the in-drag full-size display problem?]]
→ Ability to put data in the cloud


---
This page is auto-translated from [/nishio/2021-07-28Movidea開発日記](https://scrapbox.io/nishio/2021-07-28Movidea開発日記) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.