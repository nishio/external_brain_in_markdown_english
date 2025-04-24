---
title: "The line gets thinner when you tap in a group."
---

from [[pRegroup2020]]
The line gets thinner when you tap in a group.

![image](https://gyazo.com/f7f1eec904b80052eddd08295d8ec071/thumb/1000)
Originally by
![image](https://gyazo.com/3550b55aae5fc02e030829a0c7dca9c2/thumb/1000)

- DefaultTool's highlight thickens the thickness of the sticky's border.
    - And then deselect to return to oldStrokeWidth.
    - But oldStrokeWidth this is one whole
    - As a result, the paths in the sticky are also as thin as the sticky's borders.
- To begin with, when you select a sticky, there is no need to update strokeWidth all the way down to its child stickies and paths.
- Not code that explicitly updates the strokeWidth of the child
    - Change spills over to children when the target of highlighting is Group
    - Changed to highlight the `children[0]` (background shape) if it is a Group.

[[pRegroup-done-2019]] 6faffe0
---
This page is auto-translated from [/nishio/グループの中をタップした時に線が細くなる](https://scrapbox.io/nishio/グループの中をタップした時に線が細くなる) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.