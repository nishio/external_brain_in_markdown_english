---
title: "Code traps that can be used for multiple purposes"
---

![image](https://gyazo.com/d9ce4b145beea57403ea07ee3815c956/thumb/1000)
Sometimes when you are making software, you think, "This can be used for both objective A and objective B.

Being usable for multiple purposes is better than being usable for a single purpose.
- People who only use it for purpose A will simply ignore the function for B.
    - Not so much when you can't ignore it (menus are messy, buttons are all over the place, controls are more difficult to use, etc.).

However, it is not a good idea to aim to be able to use it for [[Multiple Purposes]] while "usable for a single purpose" has not been achieved.
- In the figure, assume that the shaded area is code that has already been implemented.
- The top priority is to implement x to achieve objective A
    - But x is useless for objective B.
- z is paramount to achieving objective B
    - Not useful for Objective A.
    - If you are aiming for [Multiple Purposes
    - I would give priority to implement y useful for both purposes.
    - This is because [[Objective is ambiguous]], and it's not going straight to any of the objectives.
        - Both objectives are delayed.
            - [[He who runs after two hares will catch neither]]
        - Certain patterns of creating game libraries without creating games
            - I use only library code that could be used for many different things without completing a single game.
- The reason why we recommend the development method of "decide the most important [[user story]] and aim to achieve it" is to avoid falling into this [Objective Lost

- [[Multiple Purposes]]
- [[Objective.]]

relevance
    - It came to me while writing [[Countering the Objectification of Means]].

---
This page is auto-translated from [/nishio/複数の目的に使えるコードの罠](https://scrapbox.io/nishio/複数の目的に使えるコードの罠) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.