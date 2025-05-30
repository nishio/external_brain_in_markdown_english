---
title: "Fennic tree"
---

Tree structure that allows efficient both partial sum computation and element updating
[Fennic tree - Wikipedia](https://ja.wikipedia.org/wiki/%E3%83%95%E3%82%A7%E3%83%8B%E3%83%83%E3%82%AF%E6%9C%A8)
    - In [[anthology]] it's called [[Binary lndexed Tree]].
- Abbreviated as [BIT
- [[fenwick tree]]

[No Binary Indexed Tree](http://hos.ac/slides/20140319_bit.pdf)
- > Kazuhiro Hosaka (Department of Mathematics, The University of Tokyo)
- >  13th JOI Spring Training Camp
- >  2014/03/19

Can be used as a data structure for fast retrieval of the kth value
- Adding and deleting to a set and getting kth
    - A simple way to do this is to prepare an array of size D of the value range and set 1 where there is a value
            - [[Exchange of value range and definition range]]
        - If it is changed to increment, it can be used for cases where there are multiple values of the same value ([[multiset]]).
        - Can be added and deleted with O(1)
        - Acquisition of KTH is slow because it counts from the end.
        - Make this a BIT.
    - BIT is a partial sum of O(logD)
        - We can do a bifurcated search for this.
        - O(logD) see Hosaka's data if you devise it.
    - However, additions and deletions are O(logD)
        - Compressing D with [[coordinate compression]] is effective
    - When you want to know the next value of a value in a set
        - First take the sum up to that value, add 1, and search for the bisection
        - If we repeat this, we can also "get something larger than a certain value.

- ref [Summary of data structures for fast kth value retrieval - BIT on binary search, equilibrium binary search tree, etc. - Qiita](https://qiita.com/drken/items/1b7e6e459c24a83bb7fd)
    - [Data structure that manages the kth smallest value obtainable set - kazuma8128's blog](https://kazuma8128.hatenablog.com/entry/2018/06/20/210631)

python

```
N = 1000
bit = [0] * (N + 1)  # 1-origin
 
def bit_add(pos, val):
    x = pos
    while x <= N:
        bit[x] += val
        x += x & -x  # (x & -x) = rightmost 1 = block width


def bit_sum(pos):
    ret = 0
    x = pos
    while x > 0:
        ret += bit[x]
        x -= x & -x
    return ret


def bit_bisect(lower):
    "find a s.t. v1 + v2 + ... + va >= lower"
    x = 0
    k = 1 << (N.bit_length() - 1)  # largest 2^m <= N
    while k > 0:
        if (x + k <= N and bit[x + k] < lower):
            lower -= bit[x + k]
            x += k
        k //= 2
    return x + 1


bit_add(12, 1)
bit_add(34, 1)
bit_add(56, 1)
print(bit_sum(20))  # => 1
print(bit_sum(40))  # => 2
print(bit_sum(60))  # => 3
print(bit_bisect(2))  # => 34
```


[https://judge.yosupo.jp/submission/12646](https://judge.yosupo.jp/submission/12646)

- [[data structure]]

---
This page is auto-translated from [/nishio/フェニック木](https://scrapbox.io/nishio/フェニック木) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.