---
title: "DP P"
---

[P - Independent Set](https://atcoder.jp/contests/dp/tasks/dp_p)
- Paint the given tree in black and white, black vertices must not be adjacent, count up how many ways there are.
- Just as a DP could be made "from end to end" and "looking only at the immediate front" in a linear dependency, a DP can be made "from leaf to leaf" and "looking only at the root of the tree" in a tree-structured dependency [[wood DP]].
- ![image](https://gyazo.com/10a0e781f27b7b7fc988257afad814b8/thumb/1000)
- We are using recursion where we follow the tree, but since the target is a tree and there is no confluence, there is no need to make it a memoized recursion.
python

```
def solve(N, edges):
    def visit(parent, self):
        if parent != 0 and len(edges[self]) == 1:
            # self is leaf
            return (1, 2)  # white, total

        black = 1
        white = 1
        for child in edges[self]:
            if child == parent:
                continue
            w, t = visit(self, child)
            black *= w
            black %= MOD
            white *= t
            white %= MOD
        ret = (white, white + black)
        return ret

    return visit(0, 1)[1] % MOD
```

PyPy TLE [https://atcoder.jp/contests/dp/submissions/15078877](https://atcoder.jp/contests/dp/submissions/15078877)

Cython
- [https://atcoder.jp/contests/dp/submissions/15078970](https://atcoder.jp/contests/dp/submissions/15078970)

---
This page is auto-translated from [/nishio/DP P](https://scrapbox.io/nishio/DP P) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.