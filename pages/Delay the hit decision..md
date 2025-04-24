---
title: "Delay the hit decision."
---

![image](https://gyazo.com/ecb4993fb5c02c5dfeb708648f3ed4f3/thumb/1000)

Top is before correction, bottom is after correction.
In the same way, handwriting can cause heavy processing in the writing process, which causes events to be missed and the text to be misshapen.

In this case.
- When a stylus pen-down occurs, in lasso mode, the "selection start" and "selection area movement" processes switch depending on whether or not there is a selection area at the pen-down position, so a hit judgment is necessary.
- In handwriting mode, I was doing the hit-and-run first, even though I didn't need to.
The only thing I did to improve the situation was to change the hit judgment to after the mode judgment.

I'll look into it later, as there seems to be another delay in the first stroke of handwriting.
- →Ignored because it was an initialization of the developer tools.

You can draw this much on a real machine.
![image](https://gyazo.com/187eae9fbed974d4227f5aac4551acb3/thumb/1000)

[[pRegroup-done-2020]]

---
This page is auto-translated from [/nishio/当たり判定を遅らせる](https://scrapbox.io/nishio/当たり判定を遅らせる) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.