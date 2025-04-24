---
title: "Improved Tool selection"
---

from [[pRegroup2020]]
Improved Tool selection
    - I'm doing the "setState after reading Tool#activate in Paper.js" and it's a bug where I forgot to setState.
    - To begin with, "Tool#activate is called by setState→useEffect" is correct.
    - I don't remember where it was written, but the idea is "[[single source of truth]]".
    - React should have been the single source and the Paper.js side should have been subordinate and updated when editing there.

---
This page is auto-translated from [/nishio/Tool選択を改善](https://scrapbox.io/nishio/Tool選択を改善) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.