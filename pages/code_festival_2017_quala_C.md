---
title: "code_festival_2017_quala_C"
---

[C - Palindromic Matrix](https://atcoder.jp/contests/code-festival-2017-quala/tasks/code_festival_2017_quala_c)
- ![image](https://gyazo.com/c32e2bc86779703edecaefd6b7c69127/thumb/1000)

- Thoughts.
    - If you actually rearrange and check, etc., you obviously won't be able to do it in time, so some kind of saving is necessary.
    - When the side is odd, all letters except the center are even or have even numbers; when the side is even, all letters have even numbers.
    - I'm just trying to determine if it exists or not, so why not just count the frequency and see if it's even or odd?
- Official Explanation
    - Overlooking the problem condition, it is a palindrome, even vertically.
    - The same case can be made for whether the vertical is odd or even, and the number of letters needed for one, two, or four can be determined.

---
This page is auto-translated from [/nishio/code_festival_2017_quala_C](https://scrapbox.io/nishio/code_festival_2017_quala_C) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.