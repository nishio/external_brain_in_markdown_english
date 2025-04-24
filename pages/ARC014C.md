---
title: "ARC014C"
---

[C - Where Souls Return](https://atcoder.jp/contests/arc014/tasks/arc014_3)
- ![image](https://gyazo.com/913d5c6fe52dfe68b9aa345fe3cb9899/thumb/1000)
- Thoughts.
    - It's stacked, so you can't just remember the colors on the edges, because after they disappear, the colors inside appear.
    - There are up to 50 balls and 2^50 options.
    - Whether or not it is always okay to erase when you can.
        - It's easy if you can prove you can turn it off.
        - If you can't erase it, you can always erase it next time by putting it in such a way that the same color as the next color among the three colors on the left, right and current color is exposed.
        - This way, if the length is 2, the next is 1 or 3, and that 3 is always 2 next
        - Solve the short sequence by force and see if it looks OK.
    - I think I can make it about 2^21.
- Official Explanation
    - No, there is a user commentary: [https://kort0n.hatenablog.com/entry/2020/01/08/002039](https://kort0n.hatenablog.com/entry/2020/01/08/002039)
    - The above procedure can maintain less than 3 pieces at all times.
    - No need to go through a complicated state because it can maintain it until the end of the station.
        - The logic is: [Optimal solution because it matches the lower boundary.

---
This page is auto-translated from [/nishio/ARC014C](https://scrapbox.io/nishio/ARC014C) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.