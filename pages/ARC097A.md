---
title: "ARC097A"
---

[C - K-th Substring](https://atcoder.jp/contests/arc097/tasks/arc097_a)
- ![image](https://gyazo.com/20f3988bd3141fc810146d59caf944cd/thumb/1000)
- Thoughts.
        - Create [[suffix array]]?
    - String length is 5000 at most, so normal sorting would work.
    - K is up to 5, which is awfully small.
    - If the first line of the suffix array does not get K suffixes, skip the LCPs and go to the next line.
- Official Explanation
    - Much different policy.
    - Enumerate all subcolumns, sort, uniq
    - That's too slow, so use the fact that you only get K or less to reduce the number of candidates.
    - If you can do it with a suffix sequence policy, that would be lighter.

---
This page is auto-translated from [/nishio/ARC097A](https://scrapbox.io/nishio/ARC097A) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.