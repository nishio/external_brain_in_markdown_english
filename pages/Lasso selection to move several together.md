---
title: "Lasso selection to move several together"
---

from [[pRegroup-done-2019]]
Lasso selection to move several together
- I want to move all selections together.
    - It's about time we had the ability to move all the selections together after selecting them.
    - It's about time I had a hard time, diagram.
        - [https://gyazo.com/4abea5a422fbae419de3a2816cc35260](https://gyazo.com/4abea5a422fbae419de3a2816cc35260)
    - Without collective movement of selected objects, it is not possible to organize them together when the information increases beyond a certain level...
    - If we dare to limit the functionality to what we have now, it could be possible to group them and move them around,
        - There is not yet the ability to move grouped stickies out of the group or move them within the group.
        - Once grouped together, they become fixed.
---
- The move is implemented in a separate tool to begin with.
- Do not commonize.
    - A single move in DefaultTool will eventually be added to a Group's children or something if it is dropped into a Group.
    - On the other hand, if I am moving multiple selections in LassoTool and some of the selections come on top of the Group, it would be strange if they are added to the children.
        - No, not really?
            - If the mouse pointer ends up on top of a group, should all the multiple selections be added to the group?
- I knew I shouldn't have, the abstraction is different in these two tools.
    - On the DefaultTool side, the behavior depends on the object that was there when it was first MouseDown.
    - The LassoTool side moves parallel to the selected object independently of it.

I could implement it.
→ [[Ensure that the selection state is maintained after multiple lasso moves]]
---
This page is auto-translated from [/nishio/投げ縄選択で複数まとめて移動](https://scrapbox.io/nishio/投げ縄選択で複数まとめて移動) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.