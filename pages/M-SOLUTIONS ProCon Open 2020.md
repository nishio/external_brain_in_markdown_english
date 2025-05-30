---
title: "M-SOLUTIONS ProCon Open 2020"
---

[M-SOLUTIONS ProCon Open 2020 - AtCoder](https://atcoder.jp/contests/m-solutions2020)
- I was relaxing on a 4-day weekend and I stood it up, so I solved it after the fact.

[B - Magic 2](https://atcoder.jp/contests/m-solutions2020/tasks/m_solutions2020_b)
- I thought it was a size that could be fully explored, but I determined if it was enough to find the shortest number of moves. Same as the official explanation.
python

```
def solve(A, B, C, K):
    while A >= B:
        K -= 1
        B *= 2
    while B >= C:
        K -= 1
        C *= 2
    if K >= 0:
        return "Yes"
    return "No"
```


[C - Marks](https://atcoder.jp/contests/m-solutions2020/tasks/m_solutions2020_c)
- The problem of comparing the product of multiple numbers in a moving window
- Policy of "no multiplication" as early as possible because it would mean multiplying up to 10^9 values by 200,000.
- Just compare before and after windows.
python

```
def solve(N, K, AS):
    for i in range(K, N):
        if AS[i - K] < AS[i]:
            print("Yes")
        else:
            print("No")
```


[D - Road to Millionaire](https://atcoder.jp/contests/m-solutions2020/tasks/m_solutions2020_d)
- To consider whether some kind of exploration is necessary or not, we first considered actions in the range of two or three days from the end.
- ![image](https://gyazo.com/df02ad9d7fe5c167973c1544998e93ea/thumb/1000)
- The conclusion, in essence, was to buy at all costs at the beginning of a monotonic increase and sell at all costs at the end of a monotonic non-decrease.
    - Even if there is a depression in a larger uptrend, sell just before the depression and buy at the bottom of the depression because you will do better.
    - Once that was implemented, it came down to a simple rule of action: "If the price goes up tomorrow, buy; if it goes down tomorrow, sell.
python

```
def solve(N, XS):
    cash = 1000
    stock = 0
    for i in range(N - 1):
        price = XS[i]
        if cash >= price:
            if XS[i + 1] > price:
                # buy
                s = cash // price
                stock += s
                cash -= s * price
                continue
        if stock > 0:
            if XS[i + 1] < price:
                # sell
                cash += stock * price
                stock = 0
    # last day
    cash += stock * XS[-1]
    return cash
```


[E - M's Solution](https://atcoder.jp/contests/m-solutions2020/tasks/m_solutions2020_e)
- I couldn't solve it in time.
    - I was so confident that I had arrived at the right solution that I implemented it and it didn't work.
        - Pattern where everything worked in the sample case but not when submitting
        - I found the explanation and the solution was not correct, so I'll solve it again next time.
    - Here's what I thought in time
- ![image](https://gyazo.com/4143c57fa23ff42b8189ae010fbfd7a7/thumb/1000)
    - My first thought was whether this is a matter of just adding one at a time.
        - If you look closely, you'll see that the sample presented a case where that wasn't the case.
    - What was the next thought, how many line options are there?
        - As for lines that do not pass over the city, shifting them to the side with more people will improve the score.
        - It does not get worse when the number of people is equal.
        - So you can only consider lines that pass over the city.
        - The order in which the lines are added is irrelevant.
            - So the score is a function whose domain is a subset of the line choice
            - Distance can be updated by taking min with the distance to the newly added line
            - Dynamic programming where the set is the domain and the distance is the value
        - There are 15 cities, so the line can be up to 30, the size of which can pack subsets into integers -> [[bitDP]].
- What went wrong with this policy
    - Computational complexity was not estimated correctly, 2^30 is approximately 10^10, so it was impossible to compute in a few seconds, and needed to be reduced further.
        - I wondered if it was small enough because they were censoring over the number of bottles...
        - comb(30, 15) is 1.6 * 10^8
    - 3^15 would be about 1.4 * 10^7 (I couldn't do this calculation by heart).
        - If a line passes through a city (north-south in wlog), that city has a distance of 0 regardless of the placement of subsequent lines, so no east-west line passes through it unless there are cities aligned east-west.
    - The commentary discusses reducing N^2 to N in addition to this
        - I think N if we use "Distance can be updated by taking min with the distance to the newly added line."
- PS: To begin with, `[None] * (1 << 30)` is RE with MemoryError in AtCoder environment (not MLE).
    - Estimates of spatial computational quantities were lax.
    - Do not consider a subset of a set of size 30
    - Should have been 2^15+2^15 for the north-south and east-west lines separately.
        - [[half-full enumeration]]-like idea.

---
This page is auto-translated from [/nishio/M-SOLUTIONS プロコンオープン 2020](https://scrapbox.io/nishio/M-SOLUTIONS プロコンオープン 2020) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.