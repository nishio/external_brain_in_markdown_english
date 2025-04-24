---
title: "Maybe the group doesn't need a nameplate."
---

from [[pRegroup2020]]
Maybe the group doesn't need a nameplate.
- 2019-12-10 Just noticed.
- I was thinking about handling mouse events around stickies.
- Suppose this were implemented.
    - Opening and closing grouped stickies is one-tap, but it's not that frequent, so a balloon menu would be fine.
            - [[Sticky note click to open/close, not balloon menu]]
- No need for "open and close by clicking on the nameplate."
    - We just need a balloon to appear when you click on a group.
    - Now "nameplate" is explicitly specified as a nameplate attribute of the Group object
        - That's why we need "Generate stickies when creating groups".
            - [When you want to create a group, the nameplate for that group already exists.
        - Sometimes you want to change the nameplate later.
    - There is something wrong with this design.
    - Another design proposal
        - The group has several children."
        - The summary display when the group is closed is determined by its contents."
        - If there is a sticky in the top right corner, it is displayed as a nameplate sticky."
        - I think this is fine.
        - If the top right-most object is a path, just display a thumbnail of the entire path.
    - This design would
        - There is already a sticky equivalent to a nameplate -> bring it to the upper right corner and group it
        - To change the nameplate → Place the new nameplate sticky in the upper right corner.
    - Must be able to change relative position by drag-drop within a group

---
This page is auto-translated from [/nishio/グループに表札は必要ないのでは](https://scrapbox.io/nishio/グループに表札は必要ないのでは) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.