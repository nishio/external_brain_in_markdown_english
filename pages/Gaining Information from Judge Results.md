---
title: "Gaining Information from Judge Results"
---

What I'm writing here is a discussion of whether it's technically possible, and whether it's actually done is another story.

For the question, "Output -1 when there is no solution," one submits a code that always outputs -1, and 0AC gives the knowledge that "there is always a solution." I think this technique is well known.

In the development of that, when you have a WA and you wonder "at what point does it become a WA...", you can submit a code to RE when the input does not meet certain conditions, and if the WA is not reduced, then you know that it always meets those conditions at the time of the WA.

Other errors that could be intentionally caused at runtime are TLE, MLE, and OLE.
You can get about 2 bits of information with each submission... but I'm not sure if it's a quirky judge system bully...

---
This page is auto-translated from [/nishio/ジャッジ結果から情報を得る](https://scrapbox.io/nishio/ジャッジ結果から情報を得る) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.