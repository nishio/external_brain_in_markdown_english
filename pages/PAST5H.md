---
title: "PAST5H"
---

[H - Conveyor](https://atcoder.jp/contests/past202012-open/tasks/past202012_h)
![image](https://gyazo.com/f0e4b1e3e154ed74f38484fa80a6fd5a/thumb/1000)
- Initial Considerations
    - Determine if it can be moved
    - Construct a graph and DFS "can you reach the goal" from each starting point
    - 10^6 vertices, okay?
    - Many starts, one goal.
        - → [[Make the Goal the Start]]
    - The graph is made with inverted edges, and the search is made for reachable vertices with the goal as the starting point.
        - Each vertex has only 4 edges at most, so O(N) will do.
    - Consideration complete
- mounting
    - Create a graph with inverse edges and mark the vertices to be reached by the recursive call DFS from the goal.
        - [10TLE](https://atcoder.jp/contests/past202012-open/submissions/19032906)
        - I tried it out in Python 3 after the contest [14tle](https://atcoder.jp/contests/past202012-open/submissions/19032925).
    - Explore using map data without constructing a graph
        - It's noted that it was 3TLE 1MLE during the contest, but when I just submitted it again, it was [3TLE](https://atcoder.jp/contests/past202012-open/submissions/19033329), or am I mistaken?
        - In Python3, 1MLE
    - Rewrite search in recursive calls to a while loop
        - 1TLE
    - Reduce string concatenation in result output
        - Append strings to a list without joining them in a loop and join them at the end
        - AC
- consideration
    - This time, the problem conditions lead to a worst case vertex count of 10^6
    - In the case of a Python implementation with a per-vertex list, the construction cost itself is not negligible
    - Implemented reachability checks with recursive calls DFS, but [[PyPy function calls are slow]].
    - What's wrong with MLEs...
    - Not reducing string concatenation is simply inadvertent.
        - I submitted a graph that I tried to reduce only the string concatenation while building the graph just to be sure, but this was 9 TLE, so it's not the main factor.
python

```
def solve(H, W, R, C, world):
    visited = [False] * (WIDTH * HEIGHT)
    stack = {WIDTH * R + C}

    while len(stack) > 0:
        pos = stack.pop()
        visited[pos] = True

        next = pos - 1
        if not visited[next]:
            if world[next] == 1 or world[next] == 2:
                stack.add(next)

        next = pos + 1
        if not visited[next]:
            if world[next] == 1 or world[next] == 3:
                stack.add(next)

        next = pos + WIDTH
        if not visited[next]:
            if world[next] == 1 or world[next] == 4:
                stack.add(next)

        next = pos - WIDTH
        if not visited[next]:
            if world[next] == 1 or world[next] == 5:
                stack.add(next)

    for y in range(ORIGINAL_HEIGHT):
        line = []
        for x in range(ORIGINAL_WIDTH):
            pos = WIDTH + 1 + WIDTH * y + x
            if world[pos] == 0:
                line.append("#")
            elif visited[pos]:
                line.append("o")
            else:
                line.append("x")
        print("".join(line))
```



---
This page is auto-translated from [/nishio/PAST5H](https://scrapbox.io/nishio/PAST5H) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.