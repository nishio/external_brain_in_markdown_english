---
title: "1 or 2 out of 10 heavy fake coins"
---



- Compare three pieces at a time.
- T1: ((0, 1, 2), (3, 4, 5))
    - L:  ((0,), (1,), (2,), (0, 1), (0, 2), (0, 6), (0, 7), (0, 8), (0, 9), (1, 2), (1, 6), (1, 7), (1, 8), (1, 9), (2, 6), (2, 7), (2, 8), (2, 9))
    - R:  ((3,), (4,), (5,), (3, 4), (3, 5), (3, 6), (3, 7), (3, 8), (3, 9), (4, 5), (4, 6), (4, 7), (4, 8), (4, 9), (5, 6), (5, 7), (5, 8), (5, 9))
    - E:  ((6,), (7,), (8,), (9,), (0, 3), (0, 4), (0, 5), (1, 3), (1, 4), (1, 5), (2, 3), (2, 4), (2, 5), (6, 7), (6, 8), (6, 9), (7, 8), (7, 9), (8, 9))
    - If one of them drops, select two pieces from the dropped plate and compare them.
    - T2L: ((0,), (1,))
        - L:  ((0,), (0, 2), (0, 6), (0, 7), (0, 8), (0, 9))
        - R:  ((1,), (1, 2), (1, 6), (1, 7), (1, 8), (1, 9))
        - E:  ((2,), (0, 1), (2, 6), (2, 7), (2, 8), (2, 9))
        - If one of the coins drops, the coin on that plate is a false positive.
        - If there is one card left, it is one of the one not selected in T2 and one of the four not selected in T1, maybe not.
        - Plate two of each of the five undetermined pieces.
        - T3LL: ((2, 6), (7, 8))
            - L:  ((0, 2), (0, 6))
            - R:  ((0, 7), (0, 8))
            - E:  ((0,), (0, 9))
            - If it's tilted, there's one on the lowered plate, so it's fixed in one move.
            - If it does not tilt, the remaining one coin is undetermined and is determined in one move by comparing it with the determined coin.
    - If balanced at T1, there is one on both sides or one or two on the outside.
    - Compare two from one side of the plate with the remaining one (2) plus the outside one (6).
    - There is always more than one piece in the case of "there is one piece in both."
    - T2E: ((0, 1), (2, 6))
        - If the left goes down, either of the two left coins and one of the right plate of T1 are false coins.
            - L:  ((0, 3), (0, 4), (0, 5), (1, 3), (1, 4), (1, 5))
            - Two moves to be confirmed.
            - T3EL: ((3,), (4,))
                - L:  ((0, 3), (1, 3))
                - R:  ((0, 4), (1, 4))
                - E:  ((0, 5), (1, 5))
        - If right is down, either 2 is a false coin and there is one to the right of T1, or 6 is a false coin and there is 0-1 in the remainder
            - R:  ((6,), (2, 3), (2, 4), (2, 5), (6, 7), (6, 8), (6, 9))
            - Add the coin determined to be genuine to 2 and compare with the two outer coins.
            - T3ER: ((0, 2), (7, 8))
                - If the left goes down, 2 is confirmed false, and the rest is confirmed once since there are three choices.
                    - L:  ((2, 3), (2, 4), (2, 5))
                    - T4ERL: ((3,), (4,))
                        - L:  ((2, 3),)
                        - R:  ((2, 4),)
                        - E:  ((2, 5),)
                - If the right side goes down, one of those two cards is false, one decision at a time.
                    - R:  ((6, 7), (6, 8))
                - E:  ((6,), (6, 9))
                    - If it is balanced, 2 is not false, and one time determine if 9 is false.
        - If the two plates are matched, the possibility of "one on each plate" and the possibility of "6 is false" disappear, and since one or two of the remaining three plates are false, it is determined in two moves.
            - E:  ((7,), (8,), (9,), (7, 8), (7, 9), (8, 9))
            - T3EE: ((7,), (8,))
                - L:  ((7,), (7, 9))
                - R:  ((8,), (8, 9))
                - E:  ((9,), (7, 8))

---
This page is auto-translated from [/nishio/10枚中1〜2枚が重い偽コイン](https://scrapbox.io/nishio/10枚中1〜2枚が重い偽コイン) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.