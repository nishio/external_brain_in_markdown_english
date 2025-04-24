---
title: "Kozaneba Development Diary 2022-05-27"
---

prev  [[Kozaneba Development Diary 2022-05-26]]

from [/villagepump/workroom 2022/05/27](https://scrapbox.io/villagepump/workroom 2022/05/27).
<img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>
- Copy previous work to your personal project
    - I'm afraid in the future I'll be like, "Where did I write that?"
- Create a test case that reproduces the bug
    - I'd fix it if I could afford it, but I don't know, I have a lot of meetings on Fridays.

### 11:00
- <img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>🍅11:36-12:01 create a test case that reproduces the bug".
    - ![image](https://gyazo.com/82a8445474eaabc2139c9d10c5e72af8/thumb/1000)
    - Okay, I see what you mean. You are looking at the direction of the vectors of the "midpoint" and the "intersection" when calculating the direction of the arrow, but when one is larger than the other, the midpoint can be inside the other ✅.

### 12:00
- <img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>fixed
    - ![image](https://gyazo.com/39a854eb2d297aa715a8365092d58e95/thumb/1000)
    - Another issue
        - ![image](https://gyazo.com/a8addf0eb36bc6649ba5c40a7da65e98/thumb/1000)
        - The titled group is longer on top by the height of the title, but it is mishandled and misaligned.
        - The algorithm for determining the intersection of the bounding box and the line segment assumes that "the line segment must be out of the center of the bounding box," and that was certainly fine in the past, but now the group gets a heading and extends a little higher.

### 14:00
- <img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>🍅14:40-15:05 cont.
    - Math...
    - Only one of the four directions is buggy✅.
### 15:00
- <img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>🍅15:12-15:37 cont.
    - ![image](https://gyazo.com/95d745ca2084c44cb71ab0dbe9ade462/thumb/1000)![image](https://gyazo.com/c06506e95d0089722777159ee133009d/thumb/1000)
        - fixed!
    - For some reason the border is not included in the bounding box... ✅

### 16:00
- <img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>break
    - For some reason, by not including the border in the bounding box, the tip of the arrow is cutting into the inside 5px more than expected, but I have no idea why.
        - Maybe I'm just tired.

## 2022-05-30
### 15:00
- <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>🍅15:56-16:21 Continued debugging of the problem with the arrow leading into the border".
    - ![image](https://gyazo.com/eb07b6b8d54e736161f19500b872add9/thumb/1000)![image](https://gyazo.com/5d51e17224a24707198005ac057ece9b/thumb/1000)
    - It's not that the bounding box doesn't reflect the border, it's that the arrow is stuck in the border because the subsequent drawing "draws the border outside the bounding box" whether the border is included or not.
    - Or this: [box-sizing - CSS: Cascading Style Sheets | MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/box-sizing)

### 16:00
- <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>🍅16:25-16:50 Simply changing the box-sizing is not enough.
    - ![image](https://gyazo.com/2f0eaaaab94f3d3c4ba891f0770180d1/thumb/1000)![image](https://gyazo.com/398d97b677c1f95c37717d98a6f4c41e/thumb/1000)
    - W fixed in 2min.
    - ![image](https://gyazo.com/52c95b42d976827a553cc2232f76dd03/thumb/1000)
        - It's fixed!
    - Difficult to convey before and after
        - ![image](https://gyazo.com/757cc4269c3629452d0d721449244eb0/thumb/1000)![image](https://gyazo.com/555d759b4e678c4fc495602af275204e/thumb/1000)
    - I have an extra 15 minutes to wash the next task.
    - [[FaviconAPI]] support
        - ![image](https://gyazo.com/d79f7aa115b05c609767ecd0a3578068/thumb/1000)
        - Which z-index is better?
            - ![image](https://gyazo.com/f8bd355cf07615347cfaae297628ae55/thumb/1000)

### 17:00
- <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>🍅17:14-17:39 Favicon appearance improvements.
    - Is it because of the baseline that the bottom line is not aligned with the image and the icon?
    - [vertical-align - CSS: Cascading Style Sheets | MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/vertical-align)
    - vertical-align: text-bottom
    - The z-index is larger than the text and more likely to make sense even if it's partially hidden, so I decided to put it behind.
    - ![image](https://gyazo.com/a2c4c79ae9cae536ae7d5325a3824ac1/thumb/1000)
    - 16 extra minutes to find out about the tutorial's multilingual support.
        - [Navigator.language - Web APIs | MDN](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/language)
js

```javascript
> window.navigator.language
< 'en-US'
```

        - When in Japanese, it becomes ja.
        - Data structure can complicate TypeScript types if you try to do it messy, so you have to think about it properly.

---
This page is auto-translated from [/nishio/Kozaneba開発日記2022-05-27](https://scrapbox.io/nishio/Kozaneba開発日記2022-05-27) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.