---
title: "Keicho-Mattermost State Transitions"
---

from [[pKeicho]]
Keicho-Mattermost State Transitions
- (7/2019) Current State Transition
    - State 1
        - If the number of key phrases exceeds 10, double the score of the highest scoring one and go to state 2
            - That we "chose keywords to focus on."
                - [[Transition Conditions]]
                - Now I'm simply looking at the number of key phrases, but it should be the number of those that exceed paramA (the line that prioritizes questions that don't take keywords).
            - I'm fiddling with the score to keep it in focus, but is that appropriate? Would it be better to make a "list of words in focus"?
                    - [[Score = development, not attention]]
    - State 2
        - If key phrases exceed 30, go to 21.
        - Maybe this should really be "more than a few well-developed symbols".
    - State 21
        - Question #22.
            - NoArgQuestion("What do you value?")
        - Double the score for words included in the answer.
        - Go to state 3.
    - No particular change from state 3.
        - There should be a transition to exit preparation
                - [[End Design]]

---
This page is auto-translated from [/nishio/Keicho-Mattermostの状態遷移](https://scrapbox.io/nishio/Keicho-Mattermostの状態遷移) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.