---
title: "2 out of 10 heavy fake coins."
---

Q: When two of the ten coins are heavy counterfeit coins, what is the best move to find them in the balance (assuming the counterfeit coins are of equal weight)?
[Discussion on Facebook at](https://www.facebook.com/nishiohirokazu/posts/10224642622509526)

Nishio's solution
- This is the best possible move since it is impossible in 3 moves.
- Basic Policy Explanation
    - If two of the ten coins are heavy coins, there are 45 possibilities at 10C2.
    - If three coins are placed on each side, there are 15 ways that the left side will tilt, which is exactly 1/3 the probability of 7C2=21 with no false coins on the right side minus 4C2=6 with no coins on either side.
    - This is the most informative way to divide the data, so this is the first move.
    - Since the choice of how to put it on the plate is not narrowed by previous choices, the optimal solution is obtained by the greedy method, which always makes the choice that maximizes the amount of information
- Explanation of specific methods
    - Call each coin 0-9.
    - Turn 1 is called T1.
    - T1: Compare 3 cards at a time
        - If one side drops at T1
            - T2: Select two pieces from the lowered plate and compare them
                - If one side drops
                    - The coins on that plate are false positive.
                    - The remaining one card is one that was not selected in T2 and one of the four cards not selected in T1
                    - T3: Divide these 5 pieces into 2 pieces 2 pieces 1 piece
                        - If the candidate becomes two cards, it can be fixed in one move (T4).
                - In case of a balance
                    - Either those two coins are heavy, or the one not chosen at T2 is heavy and there is one heavy coin among the four outside coins.
                    - Compare the two cards on T2 with two of the four cards on the outside." If the left goes down, those two cards are heavier. If it balances (since the left is zero), the right is also zero, or one of the two outside. If the right goes down, one of those two cards.
        - If balanced at T1
            - T2: Compare one piece from each plate with two of the four pieces you did not put on the plate.
                - If the left drops at T2
                    - I have one or two of those two cards.
                    - T3: Compare these two pictures
                        - If there was fishing, then those two pieces are false.
                        - If not balanced, the heavier one is false.
                            - Since they were balanced at T1, the remaining one is one of the two coins on either side of the four coins that were placed on the plate at T1 that did not have false coins
                            - Two candidates can be identified in one move (T4)
                - If the right side drops at T2
                    - I have one or two of those two cards.
                    - T3: Compare these two pictures
                        - If there was fishing, then those two pieces are false.
                        - If not balanced, the heavier one is false.
                            - Since we have balanced at T1, the remaining one is one of the two that we have not yet put on the plate.
                            - Two candidates can be identified in one move (T4)
                - If balanced at T2
                    - No fake coins in this one.
                    - If there are false coins, then there would be one on the left and one on the right, which would be inconsistent with the fact that they were balanced at T1.
                    - The remaining possibilities are "there is one coin on each side of the coin you put on the plate at T1 that you did not choose at T2" or "the two coins you have not put on the plate so far are false".
                    - T3: Compare the two "coins placed on the left plate in T1 that were not selected in T2".
                        - If there was fishing, "the two pieces I haven't put on my plate so far are fake."
                        - If the two cards do not match, one card on the side that has moved back is determined to be false.
                        - The remaining one is placed on the opposite plate at T1 and either of the two pieces not chosen at T2.
                        - Two candidates are confirmed in one move (T4).

detail
- Call each coin 0-9.
- T1: (0, 1, 2), (3, 4, 5)
    - Compare three pieces at a time.
    - left: ((0, 1), (0, 2), (0, 6), (0, 7), (0, 8), (0, 9), (1, 2), (1, 6), (1, 7), (1, 8), (1, 9), (2, 6), (2, 7), (2, 8), (2, 9))
    - equal: ((0, 3), (0, 4), (0, 5), (1, 3), (1, 4), (1, 5), (2, 3), (2, 4), (2, 5), (6, 7), (6, 8), (6, 9), (7, 8), (7, 9), (8, 9))
    - right: ((3, 4), (3, 5), (3, 6), (3, 7), (3, 8), (3, 9), (4, 5), (4, 6), (4, 7), (4, 8), (4, 9), (5, 6), (5, 7), (5, 8), (5, 9))
    - left T2: ((0,), (1,))
        - If one of them drops, select two pieces from the dropped plate and compare them.
        - left: ((0, 2), (0, 6), (0, 7), (0, 8), (0, 9))
        - equal: ((0, 1), (2, 6), (2, 7), (2, 8), (2, 9))
        - right: ((1, 2), (1, 6), (1, 7), (1, 8), (1, 9))
        - left T3: ((1, 2), (6, 7))
            - If one of the coins drops, the coin on that plate is a false positive.
            - The remaining one card is one that was not selected in T2 and one of the four cards not selected in T1
            - Divide these 5 cards into 2 2 1 cards (the computer has a slightly tricky way of dividing them, but you can use 2 cards on each side for the undetermined).
            - If the candidate gets to two cards, it can be fixed in one move.
            - left: ((0, 2),)
            - equal: ((0, 8), (0, 9))
            - right: ((0, 6), (0, 7))
        - equal T3: ((0, 1), (6, 7))
            - If balanced, either those two coins are heavy, or the one not chosen at T2 is heavy and there is one heavy coin among the four outside coins.
            - Compare the two cards on T2 with two of the four cards on the outside." If the left goes down, those two cards are heavier. If it balances (since the left is zero), the right is also zero, or one of the two outside. If the right goes down, one of those two cards.
            - left: ((0, 1),)
            - equal: ((2, 8), (2, 9))
            - right: ((2, 6), (2, 7))

    - equal T2: ((0, 3), (6, 7))
        - If balanced, compare one from each plate and two of the four that were not placed.
        - left: ((0, 3), (0, 4), (0, 5), (1, 3), (2, 3))
        - equal: ((1, 4), (1, 5), (2, 4), (2, 5), (8, 9))
        - right: ((6, 7), (6, 8), (6, 9), (7, 8), (7, 9))
        - left T3: ((0,), (3,))
            - If the left goes down, there are one or two of those two pieces.
            - If you compare these two cards and they are balanced, then the two cards are false.
            - If not balanced, the heavier one is false.
                - Since they were balanced at T1, the remaining one is one of the two coins on either side of the four coins that were placed on the plate at T1 that did not have false coins
            - left: ((0, 4), (0, 5))
            - equal: ((0, 3),)
            - right: ((1, 3), (2, 3))
        - equal: ((1,), (2,))
            - If balanced, there are no false coins in this
            - If there are false coins, then there would be one on the left and one on the right, which would be inconsistent with the fact that they were balanced at T1.
            - The remaining possibilities are "there is one coin on each side of the coin you put on the plate at T1 that you did not choose at T2" or "the two coins you have not put on the plate so far are false".
            - So compare the two "coins placed on the left plate at T1 that were not selected at T2".
            - If there was fishing, "the two pieces I haven't put on my plate so far are fake."
            - If the two cards do not match, one card on the side that has moved back is determined to be false.
            - The remaining one is placed on the opposite plate at T1 and either of the two cards not chosen at T2. Since there are two candidates, it takes only one move to finalize.
            - left: ((1, 4), (1, 5))
            - equal: ((8, 9),)
            - right: ((2, 4), (2, 5))
[src](https://github.com/nishio/atcoder/blob/master/single/one_heavy_coin_in_10.py)

- [[Programmatic search]]

---
This page is auto-translated from [/nishio/10枚中2枚が重い偽コイン](https://scrapbox.io/nishio/10枚中2枚が重い偽コイン) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.