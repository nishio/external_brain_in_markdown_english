---
title: "Lasso selection of a portion of a grouped path"
---

- What should happen if I [[lasso choice]] a part of [[grouped path]]?
→Implemented with the hypothesis that the entire group should be selected.

after
![image](https://gyazo.com/9ac95d1deda942d5e1f737e9a56a1ded/thumb/1000)

before
![image](https://gyazo.com/aac32a67c1e28dcf04580bdb9385de5e/thumb/1000)

discussion
- When a path in a group is lassoed, which should be selected, the path or the group?
- In the past, the paths were top of the line.
    - If you didn't explicitly group them, they didn't join the group.
    - By then the yellow frame was out.
- Transparent background for groups containing only paths.
    - At that timing, only the transparent group is used to apply the hit judgment of the child element in the recurrence call.
    - As a result, "the phenomenon occurred that a path in a group was selected and no group was selected.
- If some of the paths move despite grouping
    - Expect the whole thing to move, move it, separate it, and frustrate.

Currently, it is difficult to distinguish between paths that are not grouped and those that are.
    - [[Groups containing only paths have transparent backgrounds]].
- Currently, there is no highlighting in the selected state, so it's hard to tell how much is selected.
- Highlighting makes the difference clear.
- TODO  [[Highlight selection]]

[[pRegroup-done-2020]]

---
This page is auto-translated from [/nishio/グループ化したパスの一部を投げ縄選択](https://scrapbox.io/nishio/グループ化したパスの一部を投げ縄選択) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.