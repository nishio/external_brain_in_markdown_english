---
title: "amend to state"
---

from  [[Implement adding stickies on Paper.js]]
amend to state
The state change by opening a screen and the state change by adding a sticky go into History separately, so when Undo is done, they are Undo'd separately. I think it would be better to be like git commit --amend when multiple state changes occur with one user action.

About changing the Undo unit, rather than thinking "change the Undo unit".
If you don't need to Undo back to the "A only done state" with A and B changes occurring programmatically.
I thought I just needed to pop one from History for Undo right after A.

[[pRegroup2020]]

---
This page is auto-translated from [/nishio/stateにamend](https://scrapbox.io/nishio/stateにamend) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.