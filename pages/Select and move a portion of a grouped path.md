---
title: "Select and move a portion of a grouped path"
---

![image](https://gyazo.com/d22469cae4f03c3557670e09c458465c/thumb/1000)
If a portion of a grouped path is lassoed
- Only paths completely enclosed by a lasso are selected.
- Only that path is moved.
- Exit the group at the time of the move.

principle
- Grouped paths must move as a single entity without lassoing the whole thing each time
    - ![image](https://gyazo.com/3f9bbf7143e67a0ec9f75a38344e9328/thumb/1000)
    - In this demo, they're lassoed to show that they're grouped together.
    - Grouping is automatic.
    - With the main use case "I use a pencil on my iPad", I can write with the pen and move it as a lump with my finger.


Previous implementations
- ![image](https://gyazo.com/b00f75bdb46ec2c477ea3011e65749e8/thumb/1000)
- Selection by lasso only for top-level objects
- If you want to move only a part of it, you need to ungroup it.


---- discussion

![image](https://gyazo.com/f416bba0ae4fd759845c879bd01f5364/thumb/1000)
If you select a portion of a grouped path, how should the movement of that selection behave?

Previous implementations:.
- Selection by lasso only for top-level objects
- So the gray "whole group" becomes the selection target, and the movement is also the whole group.
Current implementation: (1)
- Child elements are also selected by a bug (shown in red).

In fixing this bug, should we stick to the "previous behavior" or not?
Ideally, only "3" should work.
What should happen after 3 moves?
- When you move the 3 farther away, that is clearly intended to be a different group than the "rest" so the group should be split.
- What if you moved them closer together? What if you made minor modifications to the placement of the elements in the group as they are?
- Should moved items be grouped?
    - There is a concern that simply grouping moved items into deeper and deeper groups

Wife's opinion
- Only "3" moves naturally.
- I often see implementations where a group is chosen and ungroup is needed to move child elements, acceptable.
- When only "3" moves, it is unnatural for it to stay in the group
- Whether the moved items are grouped or not, ideally they should be, but even if they are not, it is acceptable.

based on this
- Move only "3."
- 3" exits the group.
- Moved items are not grouped.
"is" policy

[[pRegroup-done-2020]]
---
This page is auto-translated from [/nishio/グループ化されたパスの一部を選択移動](https://scrapbox.io/nishio/グループ化されたパスの一部を選択移動) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.