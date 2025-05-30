---
title: "PAST5N"
---

[N - Travel Agent](https://atcoder.jp/contests/past202012-open/tasks/past202012_n)
![image](https://gyazo.com/c0b27c17755f5bd753462bf179457248/thumb/1000)

- Initial Considerations
    - The problem of finding the reachable range by assuming that the edge of the bus has an upper and lower age limit and that the edge exists only when the given age falls within that range.
    - Make the age axis a time axis
            - [[Make one of the two dimensions a time axis.]]
        - Connect at the lower limit and disconnect at the upper limit.
        - Queries are read ahead, mixed and sorted.
    - In [[PAST2N]] it was Range Add, but not this time, what to do?
        - We just need to get the right and left edges of the connected range fast.
        - We can have a phenic tree with the right end and a phenic tree with the left end.
        - Given a position, finding the nearest left edge to the left of it is a binary search of logarithmic order
        - Find the nearest right edge to the right of the left edge you found, and you'll get the range.
        - If the position given in the query is in that range, that's the answer.
    - Consideration complete
- Official Explanation
    - Solution 1
            - [[Query look-ahead]]
        - Sort by Age
                - [[Make one of the two dimensions a time axis.]]
        - Whether the road is passable or not changes only twice at the highest.
            - Same as my consideration.
            - [[lower_bound of std::set]] shows the range that can be reached in logarithmic order
            - So it's an equilibrium dichotomy.
    - Solution 2
        - Let L be the max segment tree.
            - Binary search with Range max is on logarithmic order
            - A range is sought that does not violate the lower limit constraints.
        - Do the same for R


---
This page is auto-translated from [/nishio/PAST5N](https://scrapbox.io/nishio/PAST5N) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.