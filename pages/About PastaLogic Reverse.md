---
title: "About PastaLogic Reverse"
---

![image](https://gyazo.com/7a5290b8fcb4ea6b879ed13b63b22825/thumb/1000)
Question: if flags A ,B and C are on Reverse and B reverses the direction of the execution cursor, is A processed again? Or is C processed?
Answer: C.

reason
- The rulebook defines the command execution phase as follows (numbers are for illustration only)
    - > In the command execution phase, the command indicated by the execution cursor is "executed"...
    - > 1: The player who places the execute flag on the command card to be executed can use the effect on the card (or not use the effect).
    - > 2: If more than one execution flag is placed, the first flag placed first is used to select which effect is to be used.
    - > 3: Once all execution flags have been processed, move the execution cursor to the next card.
- It may be easier to understand if you imagine that the execution cursor moves for each command instead of moving for each flag. It is written like this: :
    - > In the command execution phase, the command indicated by the execution cursor is "executed".
- When B reverses the cursor's direction of travel, it is step 2 above
    - > 2: If more than one execution flag is placed, the first flag placed first is used to select which effect is to be used.
    - This step processes the flags placed on the command card first placed flag first.
    - After all of that is done, we'll get to step 3.
    - So after B is processed, C is processed next.
- After all flags have been processed, in step 3 move the execution cursor to the next card.
    - This "next card" is determined by the direction of the execution cursor at this point

digression
- On whether variant rules that also reverse the order of execution within one command can be interesting to play with
    - Nishio thinks that thinking about the rules of the game is an interesting game in itself.
    - Therefore, we encourage players to discuss with each other and if they come up with rules that they think will be interesting to play, they are encouraged to play. The rules are not absolute, but are created through discussions among players in order to make the game fun to play.
    - In this case, if the rule says that the order of execution in the command is also reversed in the case where flags A and B are on Reverse, and A is convenient in the forward direction and B is convenient in the reverse direction, then after B is reversed, it will be A's turn to be reversed, and then it will be further reversed.
        - Earlier versions didn't require life payments, so we had a stalemate.
        - In the current version, it consumes a life, so there is no stalemate, but it is likely to lead to a boring "whoever has more lives when they reach this point wins" ending.
    - The following cards have the ability to reorder the order in which the flags are executed in the command
        - ![image](https://gyazo.com/0809afc9343aaf1f16e2e1973b2ec57b/thumb/1000)![image](https://gyazo.com/256a90494aff139939fdf3b6dbc53d14/thumb/1000)
    - Also, FastPass, which adds the flag at the beginning, is more costly than AddFlag, which adds the flag at the end
        - ![image](https://gyazo.com/6d38c20056129d5088a68cf296f3afa5/thumb/1000)![image](https://gyazo.com/3ae0f2a60ccb7eac1cc7cc5d03cccc70/thumb/1000)
    - These cards are balanced based on the rule that "the flag placed on that command first in the flag placement phase will trigger first".

---
This page is auto-translated from [/nishio/パスタロジックReverseについて](https://scrapbox.io/nishio/パスタロジックReverseについて) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.