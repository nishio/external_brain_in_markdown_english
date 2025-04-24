---
title: "Kozaneba Development Diary 2022-06-09"
---

prev  [[Kozaneba Development Diary 2022-06-08]]

### 11:00
- <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>🍅11:51-12:16 ["[[requestAnimationFrame]] experiment"]
    - The original implementation called onWheel at 120call/s.
    - When I put React state updates into [[requestIdleCallback]], onWheel becomes 15call/s (why?).
    - When a previous Callback remains unprocessed, cancel it and create a new one.
        - → to get about 70call/s.
        - The wheel event is differential, so if you simply discard it, the screen will only move slowly.
            - Self-supplied and added together.
    - Hmmm, no obvious difference.
        - Maybe it's just my imagination, but I think the effect of the "update delayed by up to 100ms after wheeling" makes it "go too far beyond where I expected it to go".
        - Let's put it on hold as a feature toggle and then we'll think about it.
        - I still think it stops more snugly than it did before the change.
### 13:00
- <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>The performance problem (which I tried to solve) doesn't look like it can be solved right away, so I'll do the implementation of the features I want first, and I want to use it right away.
### 14:00
- <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>🍅14:43-15:08 [["parse Scrapbox notation to get links"]] ✅.
### 15:00
- <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>🍅15:52-16:17 [["import link"]] ✅.
    - Use [[Promise.all]] [MDN](https://developer.mozilla.org/ja/docs/Web/JavaScript/Reference/Global_Objects/Promise/all)
### 16:00
- <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>🍅16:23-16:48 continued.
    - It's done!
    - ![image](https://gyazo.com/0dbed547242f0badd75adb4e5fd93c69/thumb/1000)

[/villagepump/Kozaneba+Scrapbox](https://scrapbox.io/villagepump/Kozaneba+Scrapbox)

---
This page is auto-translated from [/nishio/Kozaneba開発日記2022-06-09](https://scrapbox.io/nishio/Kozaneba開発日記2022-06-09) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.