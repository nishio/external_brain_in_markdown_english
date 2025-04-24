---
title: "PAST3N"
---

- [[Third Algorithm Practical Skills Test]]  [[PAST3]]

![image](https://gyazo.com/26b3466b604902db61b32e3f82986ffb/thumb/1000)
[N - Replace and Reorder](https://atcoder.jp/contests/past202005-open/tasks/past202005_n)
- Thoughts.
    - A naive implementation of a query to sort a range is O(NlogN)
        - Obviously, they won't make it in time.
        - It has to be about O(logN).
        - How?
        - Swap from already sorted to swap at a high Q times, so the columns before sorting are pretty close to already sorted
        - Let's treat the sorted columns as a single chunk.
        - Represent $[x, y)$ as a tuple `(x, y)`?
        - Swap at z is $[x, y) → [x, z), [z+1, z+2), [z, z+1), [z+2, y)$.
        - Segments do not overlap, so you only need to look at the top and sort.
            - Then stick them together if they are consecutive?
        - The computational complexity of the sort is O(MlogM) using the number of times M swapped up to that point.
            - It consumes Q to increase this, so it can't be too heavy.
            - If you do the sort X times, M averages Q/X, so the overall computational complexity of the sort query is O(X Q/X log(Q/X)) = O(Q log(Q/X))
                - The average computational complexity of the entire query is less than O(logN)
                - We'll be there in time.
        - How to implement this.
            - No arrays because swapping causes object insertion.
            - But when it comes to dividing by z, I want to find the object to be divided quickly.
                - If you're going to do a binary search, it has to be an array.
                - If you make a linked list, the search is in linear order.
            - Something like this "no array, no linked list" case, often a phenic tree.
            - A set represented by a phenic tree with 1's can be dichotomized in logarithmic order like an array, but insertion and deletion are in constant order.
            - However, this is unordered, so we need to order it separately in the linked list.
            - I want to find the corresponding node in the linked list in constant order after finding it in a binary search.
            - This can be accomplished with [Scarce Linked List
                - Use mostly empty, having reserved an array of size N first.
        - So this will work.
            - ![image](https://gyazo.com/95f13e11267e5141c0af54f9673191d1/thumb/1000)

- mounting
    - How do you do the sorting?
    - Oh, not with the previous diagram.
        - This has the "start value of the fragment" in the phenic tree, but the actual sort and swap query is on the "position in the array".
        - It has to be searchable.
    - I'd rather not need a linked list because the before and after values can be obtained from a bifurcated search of the phenic tree.
    - ![image](https://gyazo.com/9b21a8ee557b8855ed9b46e4621182d7/thumb/1000)
    - The difference between start and end shows where the "next fragment" is in constant order.
    - The implementation of the phenic tree was 1-origin, which was confusing, so the interface was changed to 0-origin.
    - I'm getting confused because it's so hard to distinguish between cases.
        - ![image](https://gyazo.com/c20874fb17cf8a9686e9f2d724e6e50f/thumb/1000)
- pause
- If you look for explanations on the internet, it seems like a simpler way to do it.
- Swap increases [[number of events (e.g. accidents, crimes, meetings, housing starts, hits on a web page)]] by up to 1, swap with [[bubble sort]] decreases number of falls by 1
- Just keep track of where they've been swapped and only check there when sorting.
- I'm not sure if that's really true, but I'll try to implement that policy.
- Sample passed, judge 11 TLE.
- I didn't erase the flag once I set it.
- If you turn it off, the sample will not pass.
    - It was buggy and just happened to pass by not clearing the flag.
- A swap may result in a fall in the foreground
- Flag where it can fall over during a swap (including those done at sort time).
- Sorting is done while erasing flags.
- AC'd with this.

AC:
python

```
def solve(N, Q, QS):
    values = list(range(1, N + 1))
    ft = FenwickTree(N)

    def swap(i):
        values[i], values[i + 1] = values[i + 1], values[i]
        if i > 0:
            ft.set(i - 1, 1)
        ft.set(i, 1)
        if i < N - 1:
            ft.set(i + 1, 1)

    for t, x, y in QS:
        if t == 1:
            x -= 1
            # swap query
            swap(x)
        else:
            x -= 1
            y -= 1
            # sort query
            s = ft.sum(x) + 1
            pos = ft.bisect(s) - 1
            while pos < y:
                ft.set(pos, 0)
                while pos >= x and values[pos] > values[pos + 1]:
                    swap(pos)
                    pos -= 1
                pos = ft.bisect(s) - 1

    return values
```



- [[You can only decrease the amount of increase.]]


---
This page is auto-translated from [/nishio/PAST3N](https://scrapbox.io/nishio/PAST3N) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.