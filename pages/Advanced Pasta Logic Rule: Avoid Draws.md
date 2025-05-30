---
title: "Advanced Pasta Logic Rule: Avoid Draws"
---

- Like a thousand-day move in chess, a situation may arise in which both parties choose the action they want to take and the situation remains exactly the same.
- The standard rules call for a draw.
    - This is because it is difficult to explain complicated tie-breaking rules to new players, but if both sides do not understand the rules properly, the unfamiliar side will feel uncomfortable that they have been beaten by a rule they do not understand.
    - Instead, it is a design decision to draw the game and play the next game immediately, which would be more fun per unit of time.
- On the other hand, we know that some people prefer rules with clear winners and losers. The author (Nishio) is one of them. Therefore, the rules during development defined a win/loss decision without a draw.
- This is presented as an advanced rule.

stalemate resolution rules
- If the same board situation as in the past is replayed during play at the same time that the execution of one flag is completed, either player can declare "this is a stalemate".
- When a stalemate is declared, the game ends immediately. At this time, the winner is determined by the following procedure: 1.
    - The one with more lives wins.
    - In case of a tie in life, the player with the most flags on the board wins.
    - If there are the same number of flags, the one with the most flags placed at the top of the command card wins.
    - If there is also a tie, the owner of the first flag that appears wins, looking for it from the position and orientation of the program counter at the start of the game.

---
This page is auto-translated from [/nishio/パスタロジック上級者向けルール:引き分けを避ける](https://scrapbox.io/nishio/パスタロジック上級者向けルール:引き分けを避ける) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.