---
title: "Enable automated testing of apps that use paper"
---

Enable [[Automated Testing]] for apps that use [paper.js

[[paper.js]] tries to touch the canvas just by requiring it, so the default test runner in [[create-react-app]] cannot test it
:

```
Test suite failed to run
Canvas [object HTMLCanvasElement] is unable to provide a 2D context.
> 1 | let paper = require("paper");
```


So I changed it to [[jest-electron]].

from [[pRegroup-done-2020]]

---
This page is auto-translated from [/nishio/paperを使うアプリを自動テストできるようにする](https://scrapbox.io/nishio/paperを使うアプリを自動テストできるようにする) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.