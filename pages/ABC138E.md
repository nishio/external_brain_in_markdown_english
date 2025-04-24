---
title: "ABC138E"
---

[E - Strings of Impurity](https://atcoder.jp/contests/abc138/tasks/abc138_e)
- ![image](https://gyazo.com/5f6618bde9fcd97d22a92131ae77a4f2/thumb/1000)
    - [[Think in order from smallest to largest]]
    - When t is a single letter, i is the first occurrence in s
        - When it does not appear, -1
    - When t is two characters
        - First appearance after first appearance
        - naively we can find the "first occurrence after x" on the order of 10^5
        - No, because the naive way would be 10^10.
        - For example, if you pre-calculate the "next occurrence" in a 26 x 10^5 table, it will be in constant order.
        - This pretreatment is
            - Looking at the string s one character at a time, starting from the back of the string s.
                - Writing the -1
            - If a character is found, write 0, and increment thereafter.
                - Zero if found again.
            - When you get to the beginning of the string, if it is not -1, fill it from the end, incrementing while the table is -1.
            - This will fill the table in two laps at worst per letter.
        - Looking at the i+1st letter c, we can see "the number of letters after i until the next occurrence of c" in constant order.
        - Just add up these values for each letter of T.
    - [[Official Explanation OK]]

[[ABC138]]

---
This page is auto-translated from [/nishio/ABC138E](https://scrapbox.io/nishio/ABC138E) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.