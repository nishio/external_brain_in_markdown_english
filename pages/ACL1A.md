---
title: "ACL1A"
---

![image](https://gyazo.com/419c5eed2447e1c5b17564f460169cba/thumb/1000)
from [[ACL1]]
ACL1A
[A - Reachable Towns](https://atcoder.jp/contests/acl1/tasks/acl1_a)
- ![image](https://gyazo.com/5112bbd589d700784b75fee59ac15f73/thumb/1000)
- Thoughts.
    - [[SCC]]`? No, [DSU] because the relationship is symmetrical.`
    - Since there are 200,000 N, there is no way to explicitly handle the presence or absence of edges.
    - Can we have a DP in some order?
        - Sort in advance
        - Take one leading (argmin x)
        - Groups are determined by comparing y
        - Take one lead from the rest.
        - The same thing over and over again.
        - Can we ignore those already in the group? →Can't.
        - There is a vertex that joins the group later in these patterns.
            - ![image](https://gyazo.com/bdcecf2ff9b7ed58a925acd41bb619d9/thumb/1000)

        - → This is no good because the number of comparisons is on the order of squared.
    - Can a single representative point for a group be determined? →No, it is not.
        - Note: This is a misunderstanding
    - If I divide by a value around the middle in a quick sort manner, would it be logN? →NG when almost all points are in discrete groups.
    - I can't think of a move to make.
- Process of occurrence of misunderstandings
    - We thought (mistakenly) that it was impossible to foresee which vertex of the group would lead to which vertex of the group the later joining vertex would lead to.
    - ![image](https://gyazo.com/c156550389503f072d7ef77e868a4f60/thumb/1000)
    - The condition "vertices are identified in decreasing order of x" is set to be foreseeable
    - The lower pattern in the figure above does not appear.
        - The new vertex (xi, yi) is to the right of the vertex (x0, y0) with the smallest x in the group ($x_i > x_0$)
            - Because there is no group that is or will be only the apex that has not been visited yet.
    - By visiting in order of decreasing x, we can say the following
        - yi < y0.
            - If not, then x0<xi and y0<yi and you're already in the group.
            - That is, the y condition is satisfied for all vertices of the group
        - If this vertex is in a group, then for some vertex (xj, yj) in the group, xi < xj
        - To determine this condition, we only need to focus on the vertex with the highest x in the group
        - → Be able to represent a group at one apex
        - [Fixing the order reduces the amount of information to remember.
- succession
    - Official Explanation Full Score Solution
        - > In the process of this operation, it is found that only the component with the smallest y-coordinate in each linkage should be kept, so the number of merge operations can be reduced to O(N) by using set and stack to manage them.
    - maspy acid
        - > Because stretching many edges reduces the number of vertices to be seen in the future, the stretching operation is only performed amortized O(N) times, and the rest can be solved by implementing this properly.
    - Consider a structure that keeps unused dots in place.
        - I wonder if it's [[Zerofill's Linked List]] because it's a Python list and deleting elements is slow...?
    - -> I don't understand the "appropriate" in "just implement it appropriately using stacks and sets".
        - In any implementation, when all the points are lined up in a right-over-right line and not connected, at each point you ask, "Is there anything with y greater than me?" about N^2/2 times...
    - [submissions:maspy](https://atcoder.jp/contests/acl1/submissions/16920107)decoding
        - Hey, this code doesn't do a big/small comparison, does it?
        - Using the one-to-one correspondence between x and y, transform the mapping from x to y and from y to x
            - I'm using [[Fennic tree]].
        - Set the definition area to the Y coordinate of the town and set 1 at the unused area.
        - If you want to find a town with y greater than y0
            - First, calculate the sum up to y0 and set k
            - If we bivariate search for "the first y for which sum is greater than or equal to k+1", we can find "the next largest y".
            - Both log N order
            - If we can find y, we can map y to x.
        - Summary: [[Deletable set with inequality condition]].

- Official Explanation O(N) Solution
    - Actually, it can be represented by a collection of squares.
        - Example of [A larger structure can be created from a bilateral relationship.
    - Connected components are aligned without gaps on the x-axis.
        - ![image](https://gyazo.com/419c5eed2447e1c5b17564f460169cba/thumb/1000)
        - Suppose there is a gap.
        - Being a connected component, there is an edge connecting the two groups, and the points at both ends of the edge are yi<yj
        - Point in the Gap
            - If y<yj, it would lead to the group on the right.
            - If yi<y, it would lead to the group on the left.
            - Therefore, it is impossible not to be connected to either group.
            - This contradicts the fact that there is a gap there.
    - The same for y from symmetry
    - Thus, we can say the following
        - ![image](https://gyazo.com/9558ab1f2a6d698b120754a1a85033ef/thumb/1000)
        - Look at the p0 with the smallest x at the undetermined vertex
        - If there can be k vertices above p0, then these are certainly connected to p0
        - 1: Once the kth vertex is found, it is determined to be connected at least up to that point.
        - 2: If all vertices up to this point are in the area of the square, then no vertex after that is connected to a vertex in this square.
            - Because the vertices that will come up in the future are lower than any other vertices.
            - If not, we'll widen the square.
            - The number of gaps on the y-axis will always be connected in the future.
    - AC
python

```
def solve(N, XS, YS):
    size = [0] * N
    x2y = [0] * N
    x2i = [0] * N
    for i in range(N):
        x2y[XS[i]] = YS[i]
        x2i[XS[i]] = i

    ymax = N - 1
    x = 0
    while x < N:
        start = x
        y0 = x2y[x]
        k = ymax - y0
        ymin = y0
        while k or ymax - ymin > x - start:
            x += 1
            y = x2y[x]
            if y0 < y:
                k -= 1
            ymin = min(ymin, y)
        end = x + 1
        s = end - start
        for x in range(start, end):
            size[x2i[x]] = s

        x += 1
        ymax = ymin - 1

    return size
```


---
This page is auto-translated from [/nishio/ACL1A](https://scrapbox.io/nishio/ACL1A) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.