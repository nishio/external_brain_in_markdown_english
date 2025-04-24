---
title: "Get HTML of the selected range"
---

js

```javascript
x = window.getSelection().getRangeAt(0).cloneContents()
div = document.createElement('div')
div.appendChild(x)
div.innerHTML
```

Document fragments cannot get innerHTML, but they can if you put them in a div.

[[pLinkSuggest]]

---
This page is auto-translated from [/nishio/選択範囲のHTML取得](https://scrapbox.io/nishio/選択範囲のHTML取得) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.