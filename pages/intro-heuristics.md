---
title: "intro-heuristics"
---

[A - AtCoder Contest Scheduling](https://atcoder.jp/contests/intro-heuristics/tasks/intro_heuristics_a)
- Two hours seemed short, but I feel like this is fine because longer would be exhausting.
- atcoder 605th. repeated attempts are hard in python. only 37 were made. couldn't even compile in numba in time.
- By the way, first of all, I repeatedly made the most advanced selections from my head to Greedy, and then I randomly shook the discount rate, which I discount ahead of time, because the pattern is "if you get a higher score in a few days and you do it now, you lose" when it is not good at what point.
- I didn't know there was a way to get it out on PyPy.
    - I tried to get it out again with PyPy and it was RE with numpy import.

NUMBA is not able to use PREF_COUNTER and it's hard to do "calculation until the last minute of time".
Maybe I was right to use PyPy instead of numpy to get it out.

[https://qiita.com/c-yan/items/ba0f5390c7ee8f1ba667](https://qiita.com/c-yan/items/ba0f5390c7ee8f1ba667)

[https://mdstoy.hatenablog.com/entry/2020/06/29/013915](https://mdstoy.hatenablog.com/entry/2020/06/29/013915)

[https://atcoder.jp/contests/intro-heuristics/submissions/14823819](https://atcoder.jp/contests/intro-heuristics/submissions/14823819)
[https://atcoder.jp/contests/intro-heuristics/submissions/14821744](https://atcoder.jp/contests/intro-heuristics/submissions/14821744)
[https://atcoder.jp/contests/intro-heuristics/submissions/14818177](https://atcoder.jp/contests/intro-heuristics/submissions/14818177)
[https://atcoder.jp/contests/intro-heuristics/submissions/14817099](https://atcoder.jp/contests/intro-heuristics/submissions/14817099)
[https://atcoder.jp/contests/intro-heuristics/submissions/14820088](https://atcoder.jp/contests/intro-heuristics/submissions/14820088)

---
This page is auto-translated from [/nishio/intro-heuristics](https://scrapbox.io/nishio/intro-heuristics) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.