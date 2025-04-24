---
title: "Trap where Width is affected by Scale"
---

Scale does not affect Pos in [[Rect Transform]], but Scale does affect Width.
- If you are not aware of this, you may unexpectedly specify a Width, Height that is too small.
    - ![image](https://gyazo.com/7b9985546531023cf170b8a4a99ca6c1/thumb/1000)
    - ![image](https://gyazo.com/7a3f200a666ff715451808bc2f2b74a2/thumb/1000)


---Log below
![image](https://gyazo.com/8b9f5b38c1364fe1e3714abb486f7453/thumb/1000)
![image](https://gyazo.com/793682c7ca0f056137239a4d97069c5e/thumb/1000)
![image](https://gyazo.com/cc843c01d1dd77c77095389ad28b1981/thumb/1000)
    - The top of [[monolith]] is used as the reference point, and the top of the text is aligned with the point -1 in the Y direction from there.

- Width is 0 right now, but if I want to Truncate it, should I set it appropriately (like 4 in this case)?
    - ![image](https://gyazo.com/fc001ca30c37b1577bdc2a6153ce217d/thumb/1000)
    - This is what happens when you don't Truncate.
    - but there was no horizontal Truncate to begin with.

- > [[Alignment]]'s up and down buttons were confused with the up and down buttons such as PowerPoint.
    - > This means whether the text is aligned at the top or bottom of the text with respect to the reference point, so the text will go to the top if you "align at the bottom," which is the opposite of the expression on the icon.
- But I guess not.
    - ![image](https://gyazo.com/7b9985546531023cf170b8a4a99ca6c1/thumb/1000)
    - ![image](https://gyazo.com/7a3f200a666ff715451808bc2f2b74a2/thumb/1000)
    - It seems that Scale does not affect Pos, but Width does.
        - I've misunderstood that until now, and it was made smaller than it was supposed to be.
        - In this situation, I'd stick to the lower end of the monolith with the bottom row.
        - The alignment appeared to be in alignment with respect to the reference point because the vertical width was smaller than expected.
    - Pos may be 0 with the monolith center as the reference point

- This is what happens when you set Wrap and Truncate
    - ![image](https://gyazo.com/620c853d795444ec47fae72b1c5a677b/thumb/1000)


---
This page is auto-translated from [/nishio/WidthにScaleが影響する罠](https://scrapbox.io/nishio/WidthにScaleが影響する罠) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.