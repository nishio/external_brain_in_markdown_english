---
title: "DP W"
---

[W - Intervals](https://atcoder.jp/contests/dp/tasks/dp_w)
- There are 200,000 columns of length 200,000 consisting of 0s and 1s, and 200,000 rules of "how many points if there is a 1 in this range", find how many points you get if you make the best column.
- What would happen if implemented naively?
    - Calculate score for each sequence of 2^200000 and max -> yikes!
    - Instead of calculating for each number sequence, can we use the results from the middle of the sequence to calculate more efficiently?

[EDPC Explanation U to Z - kyopro_friends' diary](https://kyopro-friends.hatenablog.com/entry/2019/01/12/231106)
[[starry sky tree]]
- [[Delayed Segment Trees]]

> `dp[i] = max when (having decided up to i) the last one is i. The transition is dp[i] = min(dp[j] | j=0~i-1). Then we do a adding a to dp[l~i] for the interval [l,i]. segtree to make it faster (we only need to be able to do interval add and interval min) O((N+M) log N)`
>  I didn't really typify this one (so the explanation is a bit fluffy).
[https://twishort.com/Vntnc](https://twishort.com/Vntnc)

---
This page is auto-translated from [/nishio/DP W](https://scrapbox.io/nishio/DP W) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.