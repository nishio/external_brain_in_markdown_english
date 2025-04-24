---
title: "Keyboard on iPhone sleep recovery"
---

Keyboard on iPhone sleep recovery
When the iPhone wakes up from sleep, the keyboard, which once disappeared, reappears to hide the most recent content.
ts

```typescript
let prevInnerHeight: number = 0;
setInterval(() => {
  const currentInnerHeight = window.innerHeight;
  if (currentInnerHeight != prevInnerHeight) {
    prevInnerHeight = currentInnerHeight;
    scrollToBottom()
  }
})
```


[[iOS Safari Keyboard]]

- [[Mysterious Margin Problem]]

[[pKakidashi-done]]

---
This page is auto-translated from [/nishio/iPhoneスリープ復帰時のキーボード](https://scrapbox.io/nishio/iPhoneスリープ復帰時のキーボード) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.