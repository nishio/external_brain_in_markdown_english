---
title: "Don't use a bounding box for a hit."
---

- [[Change the style after the fact]] works differently than expected at the time of implementation.
![image](https://gyazo.com/915922d327ad756758cd35e82c16089d/thumb/1000)
- I expected only the outer circle to turn red...

![image](https://gyazo.com/8e3824555cd41139ca8e18c83b1f6a22/thumb/1000)
- It is picking up the corners of the bounding box.
    - Side effect of [Bounding box to determine the pertinence of groups containing only paths
- solution
    - Keep the hit as a bounding box, but make it a target to be ignored by the lasso.
        - As for the after-the-fact style change of the path, I'm inclined to be okay with that.
    - Make the hit decision a fattened path, not a bounding box.
    - Eliminate the ability to drag a path in the first place.
        - →No, that's a hassle because you have to lasso the area every time.
            - One of the frustrations of existing note apps

→SOLUTION: [[Make the pass hit a fattened pass.]]

---
This page is auto-translated from [/nishio/当たり判定をバウンディングボックスにしてはいけない](https://scrapbox.io/nishio/当たり判定をバウンディングボックスにしてはいけない) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.