---
title: "Turn off software keyboard"
---

- In Safari on the iPhone, focus on the text area and the software keyboard is out.
    - window.innerHeight becomes smaller.
- And when I came back to look at other apps for a while...
    - Document rendering is done at a height where there is no software keyboard
        - (window.innerHeight will be larger)
    - The software keyboard is left out even though
- This results in content rendered below the software keyboard
    - I can't afford to have important content hidden away.
- Just blur when it becomes hidden by visibilitychange.

ts

```typescript
document.addEventListener("visibilitychange", function () {
  if (document.visibilityState === "hidden") {
    if (document.activeElement) {
      // @ts-ignore
      if (document.activeElement.blur) {
        // @ts-ignore
        document.activeElement.blur()
      }
    }
  }
});
```


---
This page is auto-translated from [/nishio/ソフトウェアキーボードを消す](https://scrapbox.io/nishio/ソフトウェアキーボードを消す) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.