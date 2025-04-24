---
title: "10x low-speed logic analyzer"
---

![image](https://gyazo.com/01792cf2916fe9b4083f1662d45cc46a/thumb/1000)

I wanted to observe the behavior of long width pulses in Micra, so I modified [[Logic Analyzer @ Micra]] to go forward one tick per second instead of one tick 0.1 second.

principle
- Create a signal that is off for only one of the 10 ticks and run it through the control line of the logic analyzer. The signal display only moves forward when the control line is OFF, so one second is one square.


[https://scrapbox.io/files/614886b675fea6001ff79f55.mp4](https://scrapbox.io/files/614886b675fea6001ff79f55.mp4)

---
This page is auto-translated from [/nishio/10倍低速ロジックアナライザ](https://scrapbox.io/nishio/10倍低速ロジックアナライザ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.