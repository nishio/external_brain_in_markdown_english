---
title: "Groups do not open and close when tapped in lasso mode"
---

from [[pRegroup-done-2019]]
- Groups do not open and close when tapped in lasso mode
    - Hmmm, when you click without selection in selection mode, you can determine that, but you can't do a simple transfer like just calling onclick in the default tool.
    - The default tool's side has a state at the mouse-down stage.
- Paper.js, the system is supposed to switch between tool objects and send mouse events to the currently selected tool, but this is not a good abstraction
    - Users zoom and click without regard to whether they're in lasso mode or pen mode.
    - The mode is only a value to be used as a reference, it is not reasonable to make it tightly coupled with the divisional unit of processing.
- → After the [[copy and paste]] discussion, I felt that clicking in lasso mode should bring up a balloon menu for paste
    - So cancel this task.

---
This page is auto-translated from [/nishio/投げ縄モードでグループをタップした時に開閉しない](https://scrapbox.io/nishio/投げ縄モードでグループをタップした時に開閉しない) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.