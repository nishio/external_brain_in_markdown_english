---
title: "agc016_b"
---

[https://atcoder.jp/contests/agc016/tasks/agc016_b](https://atcoder.jp/contests/agc016/tasks/agc016_b)
- Question to answer whether it is possible to satisfy
- 1 and other answers would narrow down the possibilities, but not in general.
- A difference of more than 2 in value is not right.
    - If k streets except A1, then k or k+1 streets back.
    - Removing A2 from it will reduce it by 1 or not.
- Let's say s street when not removed.
    - When one is removed, s or s-1 street
    - Let a and b be the number of responses, respectively
    - b cats only need to be that color
        - b-colored
    - At least one cat of a needs to be the same color.
        - Minimum 1 group
        - The maximum is
            - 1 at 3, 2 at 4, 2 at 5, 2 at 5
            - (a-1)/2.
    - If the number of colors does not fall within this range, NG
        - Sample 6 is NG because it has 3 colors even though it has a maximum of 2 groups.
    - If it falls within the range, can we say it's OK?
        - be able to say
- Official Explanation
    - WA: When all answers are the same, it can be either a or b
    - How can we recognize this?


---
This page is auto-translated from [/nishio/agc016_b](https://scrapbox.io/nishio/agc016_b) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.