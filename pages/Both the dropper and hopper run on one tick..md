---
title: "Both the dropper and hopper run on one tick."
---

Some sites state that "it moves 2 ticks after the signal comes in," but this is contrary to the facts observed in BE1.17.11.
- Droppers send items in one tick.
    - ![image](https://gyazo.com/d176adb444a0b0fb94f2cba97fd166b8/thumb/1000)
    - I only turned on one tick and made sure the item moved to the next hopper.
- Hopper sucks items in one tick.
    - ![image](https://gyazo.com/f359399ffc161a93182e52f9339f5e1e/thumb/1000)
    - I put the item in the hopper with no destination on the top and turned on the hopper on the bottom for one tick and confirmed that the item moved down
- Hopper sucks ignoring the feed invalidation time of the upper hopper.
    - ![image](https://gyazo.com/338b3fe2a916ee7b66a73de08f3b07c9/thumb/1000)
        - video
        - [https://scrapbox.io/files/613467d8263ed9001df9bfa1.mp4](https://scrapbox.io/files/613467d8263ed9001df9bfa1.mp4)
        - The first tick put the item in the top hopper and the second tick turned on the bottom hopper.
        - I confirmed that the item moves down on the second tick.
            - There must be a counter inside that counts the "number of ticks since the item was entered" because the sending out does not occur until 4 ticks later, but it is clear that the target counter value does not care when the item is sucked out
    - You can see that the hoppers are transported faster when lined up vertically than when lined up horizontally.
        - [https://scrapbox.io/files/61346f101923830023175336.mp4](https://scrapbox.io/files/61346f101923830023175336.mp4)

---
This page is auto-translated from [/nishio/ドロッパーもホッパーも1ティックで動く](https://scrapbox.io/nishio/ドロッパーもホッパーも1ティックで動く) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.