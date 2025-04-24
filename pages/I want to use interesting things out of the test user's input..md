---
title: "I want to use interesting things out of the test user's input."
---

I want to use interesting things out of what the test user entered [[pRegroup-done-2019]].
- Implemented results:.
    - Put the selected range into localStorage as JSON
        - `localStorage["tmp"] =  debug.exportSelectedItemsAsJSON()`
    - Import into Map by retrieving from localStorage
        - `debug.importItemsFromJSON(localStorage["tmp"])`
- It was a CUI command that looked like
    - If you put a GUI on it, it looks like "[[copy and paste]]".
---
Implementation Details
    - [[Interactive implementation in TypeScript]]

-----
- Export Groups
    - In the meantime, you can just spit out JSON to console.log.
- import
    - CUI is fine for now.
- relevance
        - [[Importing a portion of a map into another map]]


---
This page is auto-translated from [/nishio/テストユーザが入力したもののうちの面白いものを使いまわしたい](https://scrapbox.io/nishio/テストユーザが入力したもののうちの面白いものを使いまわしたい) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.