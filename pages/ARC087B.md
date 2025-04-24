---
title: "ARC087B"
---

![image](https://gyazo.com/5a94da0c2e1a0f43970c6ca3b1c71e40/thumb/1000)
- Thoughts.
    - Since the rotation is 90 degrees, the problem can be split into two independent problems in the x-axis and y-axis directions by splitting the problem with a rotation instruction.
            - [[divide into X and Y]]
    - The part followed by the forward instruction can be replaced by a number.
    - Given a set of numbers, the problem is to add or subtract them to a desired value.
    - How do you solve this...
        - At worst, there are 2000 numbers, there can be 2^2000 different expressions.
    - When there are many identical numbers, they can be processed together.
        - Example, when there are 100 1s, the reachable range is an even number from -100 to 100
- Official Explanation
    - You are right to divide it into X and Y.
    - The range of possible values is 16000 and the number of steps is 2000, so it is possible to DP in time.
    - The division into X and Y makes N^2 become 2N.

---
This page is auto-translated from [/nishio/ARC087B](https://scrapbox.io/nishio/ARC087B) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.