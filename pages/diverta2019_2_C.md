---
title: "diverta2019_2_C"
---

[C - Successive Subtraction](https://atcoder.jp/contests/diverta2019-2/tasks/diverta2019_2_c)
- ![image](https://gyazo.com/b445456237ffb73c3e17a53ff8a93a4b/thumb/1000)

- Thoughts.
        - [[Think in order from smallest to largest]]
    - When the number is two, subtract the smaller one from the larger one.
    - What about when there are three?
        - c-(a-b) is in essence c-a+b
    - That is, N/2 units are negative.
    - Then we can sort and set the smaller half to negative.
- Official Explanation
    - You're missing (a-b)-c when you have three.


---
This page is auto-translated from [/nishio/diverta2019_2_C](https://scrapbox.io/nishio/diverta2019_2_C) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.