---
title: "ABC032C"
---

[C - column](https://atcoder.jp/contests/abc032/tasks/abc032_c)
- ![image](https://gyazo.com/47719be25ce60aaeff7678ae9cd28aae/thumb/1000)
- Thoughts.
        - [[inchworm law]] ？
    - Product is monotonically non-decreasing as range is extended
        - So, when we search with a fixed starting point, once the condition is no longer satisfied, we know that nothing longer satisfies the condition
        - It's not the same as the shakitori method, or +1 to the starting point when the condition is not met, but this time it's not "maximum calculation result" but "maximum length" that's required, so there's no need to shrink the range.
                - [[The longest column that satisfies the condition]]
python

```
if f(start, start + length + 1) <= K:
	length += 1
else:
	start += 1
```

    - We can spin this around until we reach the end of the row.
    - If it takes a linear order of length time when length is long, it will be 10^10 orders of length and you won't be able to make it in time, so you need to make it a constant order.
        - You can pre-process the cumulative product, but if you multiply by one and divide by one, oh, notice.
    - I assumed the elements of a number line were greater than 1, but they're greater than 0.
        - In other words, when 0 appears, it is correct to cover the entire column.
        - When 0 does not appear, division is possible, so the product of the range can be calculated in constant order.
- Official Explanation
    - Excluding the case containing 0 is the same
    - If more than 2, length is in logarithmic order
        - I say let's compress it because we don't want one to last.
        - Now we have O(N log K)
    - Another solution explains the shakudori method.
- mounting
    - When I tried to implement it, "proceed without shrinking" was a bit cumbersome.
python

```
def solve(N, K, S):
    if 0 in S:
        return N

    start = 0
    result = 0
    end = 1
    prod = S[start]
    while end < N:
        if prod <= K:
            result += 1
            prod = prod * S[end]
            end += 1
        else:
            prod = prod * S[end] // S[start]
            start += 1
            end += 1
    if prod <= K:
        result += 1

    return result
```

- With the shaku-tori method, the length shrinks, so you need to take the max, the hassle wasn't that much different.
    - The reason why there is a check for K==0 only here is because the Shakitori method assumes that the condition is satisfied when the column is shrunk, but it is not satisfied when K==0 because it is 1 even in the empty column.
python

```
def solve(N, K, S):
    if 0 in S:
        return N
    if K == 0:
        return 0

    start = 0
    result = 0
    end = 1
    prod = S[start]
    while end < N:
        if prod <= K:
            result = max(result, end - start)
            prod = prod * S[end]
            end += 1
        else:
            prod = prod // S[start]
            start += 1
    if prod <= K:
        result = max(result, end - start)

    return result
```



---
This page is auto-translated from [/nishio/ABC032C](https://scrapbox.io/nishio/ABC032C) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.