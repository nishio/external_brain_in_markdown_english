---
title: "Cython and generator inclusions"
---

Mysterious error when using generator comprehensions in Cython
`ret = max(get_longest(v, edges, longest) for v in edges[start]) + 1`
:

```
Fatal Python error: Acquisition count is 0 (line 17220)
Python runtime state: initialized

Current thread 0x00007f4b63c4a740 (most recent call first):
<no Python frame>
```


Easy way to reproduce
- Put Link 1 code and standard input into Link 2 code test
    - [https://gist.github.com/nishio/c464319471c7382391424d60041da217](https://gist.github.com/nishio/c464319471c7382391424d60041da217)
    - [https://atcoder.jp/contests/dp/custom_test](https://atcoder.jp/contests/dp/custom_test)

Generator inclusion is not a no-no.
- The following code does not reproduce this error even though it is almost the same except that the argument longest has been moved to the global scope
    - [https://atcoder.jp/contests/dp/submissions/14913553](https://atcoder.jp/contests/dp/submissions/14913553)
    - Maybe when you convert the generator comprehensions to C, you're raising or lowering the reference count by some specific condition.
    - By the way, the above code is TLE, which means "it works, but it's slow".

---
This page is auto-translated from [/nishio/Cythonとジェネレータ内包](https://scrapbox.io/nishio/Cythonとジェネレータ内包) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.