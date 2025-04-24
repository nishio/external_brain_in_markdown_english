---
title: "Do not break a three-character Japanese line"
---

after
![image](https://gyazo.com/633f4ae1116a64b60bced9876845fed6/thumb/1000)

before
![image](https://gyazo.com/6d618fe26683a92387080c9b75224bee/thumb/1000)

I heard that the automatic font size adjustment is hard to see, so I tried various fixed font sizes.
    - [[What happens when font sizes are aligned?]]
It is easy to see that three Japanese characters are on one line without line breaks, so I adopted that part only.

- Lowering the font size limit would make the case for one or two letters unnecessarily small.
- If you put in the constraint of not breaking the line after two letters, you can't separate the four letters into two letters each.
- Prohibited line breaks with two characters only if the text is three characters long.

[[pRegroup-done-2020]]

---
This page is auto-translated from [/nishio/三文字の日本語を改行しない](https://scrapbox.io/nishio/三文字の日本語を改行しない) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.