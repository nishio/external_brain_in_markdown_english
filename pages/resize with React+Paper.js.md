---
title: "resize with React+Paper.js"
---

> data-paper-resize="true"

ts

```typescript
window.app.paper.project.view.onResize = () => {
  window.app.paper.project.view.center = center;
}
```


I haven't done it yet, but I'll make sure to [[Save previous center when moving screens]].
That way you can keep it centered when the canvas size changes as shown above.

[[Paper.js]]

---
This page is auto-translated from [/nishio/React+Paper.jsでresize](https://scrapbox.io/nishio/React+Paper.jsでresize) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.