---
title: "ABC162C"
---

> This Cython is TLE [https://atcoder.jp/contests/abc162/submissions/11811351?lang=ja](https://atcoder.jp/contests/abc162/submissions/11811351?lang=ja)
> This PyPy comes through (947ms) [https://atcoder.jp/contests/abc162/submissions/11828688?lang=ja](https://atcoder.jp/contests/abc162/submissions/11828688?lang=ja)
> Is this not a good use of Cython?
[https://twitter.com/mec287117892/status/1249333553667555340](https://twitter.com/mec287117892/status/1249333553667555340)
PyPy also JIT compiles the contents of gcd, but Cython assumes that gcd without a type declaration is a function that inserts and removes objects, so it converts variables declared as int to objects every time.

Yes, AC 785 ms for [[Cython]], faster than PyPy.
python

```
cdef gcd(int p, int q):
    cdef int r
    while q:
        r = p % q
        p = q
        q = r
    return p
 
 
def main():
    cdef int ans, i, j, l, K
    K = int(input())
    ans = 0
 
    for i in range(1, K+1):
        for j in range(1, K+1):
            for l in range(1, K+1):
                ans = ans + gcd(gcd(i, j), l)
    print(ans)
 
 
if __name__ == "__main__":
    main()
```

[https://atcoder.jp/contests/abc162/submissions/14918529](https://atcoder.jp/contests/abc162/submissions/14918529)

#atcoder

---
This page is auto-translated from [/nishio/ABC162C](https://scrapbox.io/nishio/ABC162C) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.