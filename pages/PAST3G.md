---
title: "PAST3G"
---

from  [[Third Algorithm Practical Skills Test]]
PAST3G
G
- The problem is to find the shortest path length for a Shogi Kinsho to move from the start to the goal on a grid with obstacles.
        - [[grid graph]]   [[shortest path problem]]
- Width-first search. One square outside the area where obstacles can be placed is sufficient for a detour route.
- I first squashed the bugs while debugging output with a version in which the grid size was 5x5, since it seemed to be buggy.
- The first submission exceeded the time limit because I forgot to mark the squares that had been visited. I didn't realize this when I was testing with small data.
- The second submission was a run-time error, calculating the grid size one square less. There are three squares in the -1 to 1 range.

python

```
TINY_TEST = False

if TINY_TEST:
    MIN_BOUND = -2
    MAX_BOUND = 2
else:
    MIN_BOUND = -200
    MAX_BOUND = 200

WIDTH = (MAX_BOUND - MIN_BOUND) + 4  # why not 3?
M = [["."] * WIDTH for i in range(WIDTH)]


def setMap(p, v):
    x, y = p
    M[y - MIN_BOUND + 1][x - MIN_BOUND + 1] = v


def getMap(p):
    x, y = p
    return M[y - MIN_BOUND + 1][x - MIN_BOUND + 1]


START = (0, 0)
if TINY_TEST:
    GOAL = (2, 2)

    setMap(START, "S")
    setMap(GOAL, "G")
    obstacles = [(1, 1)]
    for p in obstacles:
        setMap(p, "#")
else:
    N, X, Y = [int(x) for x in input().split()]
    setMap((X, Y), "G")
    for i in range(N):
        p = [int(x) for x in input().split()]
        setMap(p, "#")


def pp(map):
    for line in map:
        print("".join(line))


def main():

    def visit(x, y):
        if getMap((x, y)) == "G":
            return True
        if getMap((x, y)) != ".":
            return
        if x < MIN_BOUND-1 or MAX_BOUND+1 < x:
            return
        if y < MIN_BOUND-1 or MAX_BOUND+1 < y:
            return
        newFront.append((x, y))
        setMap((x, y), "v")

    newFront = [START]
    for numSteps in range(1, 1000):
        front = set(newFront)
        # print("len front,", len(front), numSteps)
        # print(front)
        newFront = []
        for x, y in front:
            isFinished = (
                visit(x + 1, y + 1)
                or visit(x, y + 1)
                or visit(x - 1, y + 1)
                or visit(x + 1, y)
                or visit(x - 1, y)
                or visit(x, y - 1))
            if isFinished:
                print(numSteps)
                return
        if not newFront:
            print(-1)
            return


main()
```


---
This page is auto-translated from [/nishio/PAST3G](https://scrapbox.io/nishio/PAST3G) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.