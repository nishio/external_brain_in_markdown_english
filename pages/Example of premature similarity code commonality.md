---
title: "Example of premature similarity code commonality"
---

- Paths are now removed from a group when a portion of the grouped path is selected and dragged.
    - This is intentional.
        - [[Select and move a portion of a grouped path]]

- If all the child elements of a group are lasso selected, it is assumed that the group is selected
    - This too is intentional.

- When you drag one thing in neither lasso nor pen mode, it is moved
    - This too is intentional.

- When a child element of a group with only one child element is dragged and moved, it leaves the group, leaving an empty group
    - This is unintentional.

- An unintended side-effect of "Move to exit group" is that when I try to adjust the position of grouped stickies within a group, they are exited from the group.
    - This is unintentional.
    - The ideal behavior is
        - Exit the group after dragging outside the group border.
        - If it's inside the border, it's just a change of position.

To summarize, the conclusion is that it was a mistake to think that multiple moves in a lasso selection and a single move could be combined in the same code.

- [[Premature commonization of similar codes]]

---
This page is auto-translated from [/nishio/早すぎる類似コード共通化の例](https://scrapbox.io/nishio/早すぎる類似コード共通化の例) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.