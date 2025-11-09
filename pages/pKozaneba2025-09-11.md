---
title: "pKozaneba2025-09-11"
---

![image](https://gyazo.com/f4fea44776b9e5848bf2384379de4dc7/thumb/1000)
Merge Behavior Changes
- Previously: Merge always created a new kozane and deleted all selected kozanes.
- After: kozane with the largest scale value remains, and the others are deleted.
- Edge case: if there is more than one largest scale, the text join logic is applied only to that largest group of kozane, leaving the first one.
    - [https://github.com/nishio/kozaneba/pull/33](https://github.com/nishio/kozaneba/pull/33)
- New Behavior
    - ![image](https://gyazo.com/33e95419f0a3af5b67ecc170813d45f1/thumb/1000)
Previous behavior
- ![image](https://gyazo.com/ded5d51cbee922f67ba98071571fa28d/thumb/1000)

Added "Scale Double" command to Group menu
- Add a new "Scale Double" to the context menu of the group. Double both the spacing (position) and size (scale) of items in a group.
- The existing "Spread" is positioned to complement it, as it only doubles the spacing between items.
- ![image](https://gyazo.com/adcf718feb2429a8babed153f70439e7/thumb/1000)
- [https://github.com/nishio/kozaneba/pull/34](https://github.com/nishio/kozaneba/pull/34)

Added Rotate/Spread/Scale Double to the Selection menu as well.
- [https://github.com/nishio/kozaneba/pull/35](https://github.com/nishio/kozaneba/pull/35)



![image](https://gyazo.com/9022c40e054c10cac7ebff0a70d6321e/thumb/1000)
Oh no, I don't know what to do.
- Devin made an implementation that asks you in a dialog when you draw a line, but it's obviously annoying.
- Add additional menus for "Labeled Lines" and "Labeled Arrows" or
- Click on a line to bring up the "Label" menu, or

---
This page is auto-translated from [/nishio/pKozaneba2025-09-11](https://scrapbox.io/nishio/pKozaneba2025-09-11) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.