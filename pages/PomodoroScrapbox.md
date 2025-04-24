---
title: "PomodoroScrapbox"
---

Select the string "Pomodoro" and press the Tomato menu to get the following notation
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>🍅03:27-03:52 Pomodoro
- [[pomodoro technique]] with the current time and the time 25 minutes later.

script.js

```javascript
scrapbox.PopupMenu.addButton({
  title: "🍅",
  onClick: (text) => {
    const name = "nishio";
    const timeFormat = (d) => {
      const h = d.getHours().toString().padStart(2, "0");
      const m = d.getMinutes().toString().padStart(2, "0");
      return `${h}:${m}`;
    }
    const now = new Date();
    const end = new Date(now.getTime() + (1000 * 60 * 25));
    return `[${name}.icon]🍅${timeFormat(now)}-${timeFormat(end)} [" ${text}]`;
  },
});
```



---
This page is auto-translated from [/nishio/PomodoroScrapbox](https://scrapbox.io/nishio/PomodoroScrapbox) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.