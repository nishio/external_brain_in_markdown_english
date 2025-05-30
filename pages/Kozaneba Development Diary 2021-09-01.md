---
title: "Kozaneba Development Diary 2021-09-01"
---

from  [[Kozaneba Development Diary 2021-08-31]]
2021-09-01Kozaneba Development Diary

When you ungroup a group with a title, the title is turned into a kozane, but if you want to group it again, it is not intuitive to do so.
For example, if the title would be an empty group with a title, you can select the element that went out and put it back in again.
- This can now be done with empty groups so they don't collapse into smaller ones.

The problem is that the name "Ungroup" does not seem to be appropriate for the function of "emptying the contents of a group (the group itself remains)".

Using this feature on a group with no title will result in an empty group and contents.
Once the automatic deletion of empty groups is entered, the behavior is exactly the same as Ungroup now.

Since the current Ungroup also has special processing to add Kozane only for groups with titles, would it be better to change that special processing? The process for groups without titles should not be changed.

![image](https://gyazo.com/efe3b7bec6ac66c20ed4cbc9e78f982d/thumb/1000)
`-349.98748446822736`
`2421.197029584663`

---
release notes
- Fixed a bug that caused a crash when MouseUp was performed on a group during range selection

---
I'd like to see the last save date and time.
Deleted or moved groups, are they saved? Check
Parallel screen movement, update timing?

release notes
- Selection can be copied (copy JSON)
- I can stick that on.
    - This JSON pasting is exposed as an API, so users can create template-like objects from a custom menu
- Last save time can be checked from the StatusBar.
- Fixed a bug where deleting groups and kozane did not trigger a save
- Zoom out with N key

Added key binding changes
arrow (mark or symbol)
- killer application
    - Source Code Dependencies

The bounding box in the image is wrong.
- Funny at the time of selection.
- Size not known until image is read at load time, should be saved.

![image](https://scrapbox.io/files/612f3dbca9bf940023907e92.png)
- [[Good to know about where Kozaneba is going next.]]
![image](https://gyazo.com/ed1b782cc5f75ac38432b464fe1c3b70/thumb/1000)

Branches should be extended.
- Current status of touch support
    - You can click to open and close the menu.
    - Cannot be moved.
    - You can zoom in and out with a two-finger pinch, but it's magnified by the browser function, and there's a zoom limit.
- arrow (mark or symbol)
    - If you create a line in SVG, it is possible to use only the line part as a hit detection.
    - How to determine the end position
        - If you want to ignore "arrow to arrow" and so on for once, just get the coordinates of the target object.
        - Arrow to arrow
            - This is also not a problem if the dependency is a tree.
            - It's bad enough that dependencies can be cycled.
    - (order of) superposition
        - Math.max with the foremost or z-index on all elements
- Once I put aside my overly strong idealistic view of the arrow function and stacking order, I thought it would be, well, easy to put the arrows on a separate layer and cover one SVG on top.

release notes
- Fixed a crash bug when ungrouping a group within a group

- [[Kozaneba Development Diary 2021-09-02]]
---
This page is auto-translated from [/nishio/Kozaneba開発日記2021-09-01](https://scrapbox.io/nishio/Kozaneba開発日記2021-09-01) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.