---
title: "When MoveFlag is incremented"
---

![image](https://gyazo.com/d1053f1cc69f81a7274bc60aaeff7b4f/thumb/1000)
>  Q1: Can MoveFlag move flags to MoveFlag?
>  Q2: If MoveFlag has an increment token placed and is at least {2} and the source command has 4 flags placed, can that command be selected as the destination for the other flag?
>  Q3: Also, if the above can be done, is it possible to move when there is a deadlock situation where two move source commands are filled with 4 flags and each other chooses the move destination

- The following is a detailed description of the MoveFlag effect.
    - 1: Choose one command other than this command (X).
    - 2: Select one flag above X (A)
    - 3: Choose one command other than X (Y).
    - 4: Move A to the end of Y.
    - 5: Repeat 1-4 {1} times.
- Q1: Can I use MoveFlag to move flags to MoveFlag?
    - I can do it.
- Q2: When there is an increment token placed on MoveFlag and it is {2} or more, and the source command has 4 flags placed on it, can that command be selected as the destination of the other flag?
    - The two moves are done sequentially, so even if X has 4 flags on it at first, if the first run of MoveFlag reduces the number of flags on X to 3, then X can be the destination on the second run.
- Q3: Is it possible to move in a deadlock situation where two move source commands are filled with 4 flags and each chooses the move destination?
    - If X and Y each have 4 flags, no move can be made that exchanges X and Y flags.
    - The two moves are done sequentially. Note the "first run."
        - If X and Y each have 4 flags, then on the first run, neither X nor Y can be chosen as the destination because they already have 4 flags.

---
This page is auto-translated from [/nishio/MoveFlagをインクリメントした時](https://scrapbox.io/nishio/MoveFlagをインクリメントした時) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.