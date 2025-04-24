---
title: "Mankara Karacha"
---

![image](https://gyazo.com/35dccc4a5700cc4f20f3e5b745a5a3b0/thumb/1000)
You can play Mancala and Karaha, two games with different rules.
- Played Mancala twice.
    - There were still some omissions in the second one, so I'd like to give it some thought.

rule
- [https://recreation.or.jp/activities/genki_up/mancala/mancala_rule/](https://recreation.or.jp/activities/genki_up/mancala/mancala_rule/)
- Two-person complete information game without the element of luck

If neither side can send any more stones to the other's position, then the one with fewer moves to the goal wins!
- However, this "stones cannot be sent to the opponent's position" was a much tougher condition than expected.
    - If a stone is in two different squares, it is possible to send it to the opponent's position by joining them in a square of 6 so that there are two stones
:
| 1 | 2 | 3 | 4 | 5 | 6 | 7 | op |
| -- | -- | -- | -- | -- | -- | -- | -- |
|  |  |  |  | o | o |  |  |
| 1 | 2 | 3 | 4 | 5 | 6 | 7 |  |
|  |  |  |  |  | oo |  |  |
| 1 | 2 | 3 | 4 | 5 | 6 | 7 |  |
|  |  |  |  |  |  | o | o |

So the actual resolution is, "It's OK if we lose our stones before they send theirs to our position."
- This is probably the longest number of moves before you can send a stone (6 moves)
:
| 1 | 2 | 3 | 4 | 5 | 6 | 7 | op |
| -- | -- | -- | -- | -- | -- | -- | -- |
| o | o |  |  |  |  |  |  |
| 1 | 2 | 3 | 4 | 5 | 6 | 7 | op |
|  | oo |  |  |  |  |  |  |
| 1 | 2 | 3 | 4 | 5 | 6 | 7 | op |
|  |  | o | o |  |  |  |  |
| 1 | 2 | 3 | 4 | 5 | 6 | 7 | op |
|  |  |  | oo |  |  |  |  |
| 1 | 2 | 3 | 4 | 5 | 6 | 7 | op |
|  |  |  |  | o | o |  |  |
| 1 | 2 | 3 | 4 | 5 | 6 | 7 | op |
|  |  |  |  |  | oo |  |  |
| 1 | 2 | 3 | 4 | 5 | 6 | 7 | op |
|  |  |  |  |  |  | o | o |
- Can be accelerated by stacking even if the opponent sends a lot of stones (* just ends and continues the turn).
:
| 1 | 2 | 3 | 4 | 5 | 6 | 7 | op |
| -- | -- | -- | -- | -- | -- | -- | -- |
| o | o | o |  |  |  |  |  |
| 1 | 2 | 3 | 4 | 5 | 6 | 7 | op |
|  | oo | o |  |  |  |  |  |
| 1 | 2 | 3 | 4 | 5 | 6 | 7 | op |
|  |  | oo | o |  |  |  |  |
| 1 | 2 | 3 | 4 | 5 | 6 | 7 | op |
|  |  |  | oo | o |  |  |  |
| 1 | 2 | 3 | 4 | 5 | 6 | 7 | op |
|  |  |  |  | oo | o |  |  |
| 1 | 2 | 3 | 4 | 5 | 6 | 7 | op |
|  |  |  |  |  | oo | o* |  |
| 1 | 2 | 3 | 4 | 5 | 6 | 7 | op |
|  |  |  |  |  |  | o | o |
:
| 1 | 2 | 3 | 4 | 5 | 6 | 7 | op |
| -- | -- | -- | -- | -- | -- | -- | -- |
| o | o | o | o |  |  |  |  |
| 1 | 2 | 3 | 4 | 5 | 6 | 7 | op |
|  | oo | o | o |  |  |  |  |
| 1 | 2 | 3 | 4 | 5 | 6 | 7 | op |
|  |  | oo | oo |  |  |  |  |
| 1 | 2 | 3 | 4 | 5 | 6 | 7 | op |
|  |  |  | ooo | o |  |  |  |
| 1 | 2 | 3 | 4 | 5 | 6 | 7 | op |
|  |  |  |  | oo | o | o* |  |
| 1 | 2 | 3 | 4 | 5 | 6 | 7 | op |
|  |  |  |  |  | oo | o* |  |
| 1 | 2 | 3 | 4 | 5 | 6 | 7 | op |
|  |  |  |  |  |  | o | o |


- Might it be important to keep the number between 2 and 9 before the goal?
    - In that state, you can send a stone to your opponent in one move.

- The following is deterministically determined for a sequence of 6 values
    - Minimum number of moves until all of them are gonea
    - The shortest number of moves to send to the opponent b
- a is up to 6
    - Monotonically decreasing unless a send-in from the opponent occurs.
- b can be infinite (cannot be fed)
    - Play it badly and you'll get more.
    - Decreased by sending from the other party
- After your turn, if your opponent's a is other than your b, you lose.

---
This page is auto-translated from [/nishio/マンカラ・カラハ](https://scrapbox.io/nishio/マンカラ・カラハ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.