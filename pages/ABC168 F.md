---
title: "ABC168 F"
---

Given 2000 vertical and horizontal line segments and a space about 10^9 wide delimited, find the area of the area reachable from the origin [problem](https://atcoder.jp/contests/abc168/tasks/abc168_f).

summary
    - [[coordinate compression]] and then just DFS the AC
- TLE when submitting
- I built the graph in advance using maspy's code as a reference, but MLE
- I thought the MLE cause was a graph represented by a dens matrix, but I was wrong.
    - It was a set that recorded visited vertices in the process of DFS [[set is a memory hog]].

-----
During the contest, I was completely untouched. Read the commentary and then give it a try.

Searching one pixel at a time is slow, so it is processed by chopping it into meaningful rectangular squares.
    - It's referred to by the term [[coordinate compression]].
- You can sort and unique the values that appear, and bisect each value against them.

First written.
- Submittal Results, 11/96 TLE [https://atcoder.jp/contests/abc168/submissions/14612194](https://atcoder.jp/contests/abc168/submissions/14612194)
    - I think this is obvious. I have the coordinates in real coordinates, and I have to bisect every time to find a neighboring vertex.
    - Let's bisect it first and use it.
- I later verified it at hand and found AC: 96, max_time: 56.97.
    - The calculations were correct, but too late.
python

```
N, M = map(int, input().split())
vlines = defaultdict(list)
hlines = defaultdict(list)
vticks = {0}
hticks = {0}

for i in range(N):
    A, B, C = map(int, input().split())
    vlines[C].append((A, B))
    hticks.add(C)
    vticks.update((A, B))

for i in range(M):
    D, E, F = map(int, input().split())
    hlines[D].append((E, F))
    vticks.add(D)
    hticks.update((E, F))

vticks = [-INF] + list(sorted(vticks)) + [INF, INF]
hticks = [-INF] + list(sorted(hticks)) + [INF, INF]


def up(y):
    return vticks[bisect.bisect_left(vticks, y) - 1]


def down(y):
    return vticks[bisect.bisect_left(vticks, y) + 1]


def left(x):
    return hticks[bisect.bisect_left(hticks, x) - 1]


def right(x):
    return hticks[bisect.bisect_left(hticks, x) + 1]


def area(x, y):
    i = bisect.bisect_left(hticks, x)
    width = hticks[i + 1] - hticks[i]
    j = bisect.bisect_left(vticks, y)
    height = vticks[j + 1] - vticks[j]
    return width * height


total_area = 0
visited = set()


def visit(x, y):
    global total_area
    if (x, y) in visited:
        return
    # dp("visited: x,y", x, y)
    a = area(x, y)
    total_area += a
    visited.add((x, y))
    # visit neighbors
    l = left(x)
    if (l, y) not in visited:
        for a, b in vlines[x]:
            if a <= y < b:
                # blocked
                break
        else:
            # can move left
            to_visit.append((l, y))

    u = up(y)
    if (x, u) not in visited:
        for a, b in hlines[y]:
            if a <= x < b:
                # blocked
                break
        else:
            # can move up
            to_visit.append((x, u))

    r = right(x)
    if (r, y) not in visited:
        for a, b in vlines[r]:
            if a <= y < b:
                # blocked
                break
        else:
            # can move left
            to_visit.append((r, y))

    d = down(y)
    if (x, d) not in visited:
        for a, b in hlines[d]:
            if a <= x < b:
                # blocked
                break
        else:
            # can move up
            to_visit.append((x, d)) 

to_visit = [(0, 0)]
while to_visit:
    x, y = to_visit.pop()
    if x == INF or x == -INF or y == INF or y == -INF:
        print("INF")
        break
    visit(x, y)
else:
    print(total_area)
```


Pre-bisect policy (proper coordinate compression)
- RE with out-of-range access by mistaking x and y
    - Corrected but also 11 TLE
    - Hmmm [[numba]].

Error on closure in numba
- I'm not sure under what conditions it happens.
- I had made the "visit" a function somehow, but I didn't want to call it recursively, so I expanded it inline.

I'm having trouble getting data in the form `int => [(int, int)]` into numba world.
- I refilled my own np.array.
- I can run it on hand and it's usually AC, but some of it is WA.
    - PS: The cause is that you forgot to add 0 to the coordinates, so when you bisect it, it goes into a different square than expected.
python

```
>>> xs = [-1, 1, 2]
>>> xs[bisect.bisect_left(xs, 0)]
1
```

    - ![image](https://gyazo.com/089dd5c0366f3fd127dcb989cdf2f247/thumb/1000)

    - I broke it in the process of porting to numba.
python

```
 vticks = {0}
 hticks = {0}
```

    - At this point, I was unaware of the cause and sought another way to pass it on (see below).

- [[Passing complex types to NUMBA]]
- You can pass dict and list, too!
- [[numba bisect]]
    - The standard library bisect does not work as it is, so I copied and pasted it into main.
    - In this case, it's a function within a function, but it works fine.
- Submit: all RE
    - atcoder's numba is 0.48 and old so typed.List can't take arguments orz
    - We should not be doing this.
        - Knowledge that "the latest version can do this, but atcoder's is an older version, so it needs to be rewritten this way" is a type of knowledge that has no other application and will become obsolete with atcoder's version upgrade, and should not be tried.
        - Knowledge that is likely to change and become obsolete in the future where the behavior changes with minor version differences.

Read others' explanations and codes.
- [https://maspypy.com/atcoder-参加感想-2020-05-18abc-168](https://maspypy.com/atcoder-参加感想-2020-05-18abc-168)
    - [tuned code](https://atcoder.jp/contests/abc168/submissions/13389928)
    - [blog posting code](https://atcoder.jp/contests/abc168/submissions/13359130)
    - [first ac](https://atcoder.jp/contests/abc168/submissions/13349468)
- `data = np.int64(read().split())`
    - Ahhh, I see. It's complicated because you have to create the structure and then figure out how to pass it on, so you pass it on as a column as you read it...
- [[numpy.unique]]
    - Similar to set, but a sorted array.
- data structure
    - My implementation is checking every time I move to an adjacent square, "Does it collide with a line segment on that line?" check.
        - So I had an `int => [(int, int)]` with a "line segment on a line" and I was having trouble numba-ing it.
    - maspy's code is a graph structure with vertices arranged in a rectangle #Rectangular graph search
        - Packs x,y into integers, so `int[:, :]`.
            - The number of edges per vertex is also fixed at 4
            - Q: What about the edges of the rectangle?
                - A: I put [[sentry]] on the end, and when it reaches it, it returns INF and ends the search, so it doesn't have to have the correct value in it.
        - I somehow assumed that it was impossible to construct a graph in the yang.
        - It seems that a scale of this size (3000 * 3000 * 4) would not be a problem.
        - If you devise it, it will be 1000 * 1000 * 4.
            - [tuned code](https://atcoder.jp/contests/abc168/submissions/13389928) pruning the end of the line segment
            - ![image](https://gyazo.com/7006b27454eb8b4aaa230b1e3c7e1fa8/thumb/1000)

What to do next
- Stop passing complex types to NUMBA.
- Try to see if you can build the same complex molds in the numba world as you do now.

`vlines[C] = []`
python

```
There are 10 candidate implementations:
   - Of which 8 did not match due to:
   Overload in function 'setitem': File: <built-in>: Line <N/A>.
     With argument(s): '(DictType[undefined,undefined], int64, list(undefined))':
    No match.
   - Of which 2 did not match due to:
   Overload in function 'impl_setitem': File: numba/typed/dictobject.py: Line 669.
     With argument(s): '(DictType[undefined,undefined], int64, list(undefined))':
    Rejected as the implementation raised a specific error:
      TypingError: list(undefined) as value is forbidden
```

`vlines[C] = [(0, 0)]`
`TypingError: list(UniTuple(int64 x 2)) as value is forbidden`

Nope, let's give up using complex types in numba.

Numba's fine story
python

```
# OK 
xticks = np.unique(np.concatenate((A, B, D, np.array([-INF, 0, INF]))))
# NG
yticks = np.unique(np.concatenate((E, F, C, [-INF, 0, INF])))
```

- The code below is an error due to mixed types in the argument tuple of np.concatenate see [[numba np.concatenate]].

`AC: 25, WA: 65, RE: 6, max_time: 0.53`
- I misunderstood how to write a horizontal line.
- RE is Segmentation fault

`AC: 96, max_time: 2.91`
- submit
    - sub1_93.txt	MLE
    - This is the first time I've ever run into a memory limit.
    - I'm new to this so I'm not sure how to deal with it, but I guess I'll just throw away A-F since I don't need them when I'm done making the graph?
    - No, you can't.
    - Try to make graph edges bool instead of int
    - Is this still not good enough?
    - I tried using scipy.sparse.[[csr_matrix]] but numba doesn't support it.

I re-read maspy's code again.
- [tuned code](https://atcoder.jp/contests/abc168/submissions/13389928) is waiting for a straightforward 4*N matrix, but
- [first AC](https://atcoder.jp/contests/abc168/submissions/13349468) do you have it in 2*|E| of vertex pairs?
python

```
def add(v, w):
    nonlocal p
    nxt[p] = head[v]
    head[v] = p
    ng[p] = w
    p += 1
```

    - Ah, I see, this is [[linked list]]!
        - p is the free position
        - The previous writing about `v' is in `head[[p]]`, so transcribe it to `next[[p]]` to connect the link.
        - head is initialized with -1, so -1 is terminal
        - ![image](https://gyazo.com/cd9568515772bf6b0b7aeb340b69bc4d/thumb/1000)

- [first AC](https://atcoder.jp/contests/abc168/submissions/13349468) is 227MB with this devise
- [blog-posted code](https://atcoder.jp/contests/abc168/submissions/13359130) is a straightforward bool matrix, 86MB
- I, on the other hand, have 1532 MB...

I don't know...
- The first code is on the link list, so it saves memory.
- The tuned code drops the ends of the lines, so the number of super points is reduced to 1/9, saving memory.
- But the blog code is normally 9_000_000 * 4 dens np.array.
    - Same as my code.
    - If there is a slight difference, why is there a 20-fold difference?

- `solve(*precompute(N, M, data))` is a two-step process.
    - have nothing to do with (something)
- Have integers in 32-bit instead of 64-bit
    - `10 ** 9 < 2 ** 31`
    - Unresolved.
- Have 16-bit compressed coordinate values.
    - `3000 < 2 ** 15`
    - Unresolved.
- Instead of having the graph as N * 4, pack 4 values into an integer and have it as uint8
    - Unresolved.
- `INF = 10 ** 9 + 1`
    - I had set `INF = 10 ** 10`, which actually exceeds Int32.MaxValue.
    - `10 ** 10 > 2 ** 31`
    - I've tried changing it, but it doesn't affect me.

I'll try [[mprof]] at hand since it doesn't solve the problem at all.
- My code
    - ![image](https://gyazo.com/b7f0e30e84651d516ec7d6e0e824edfc/thumb/1000)
- maspy's code
    - ![image](https://gyazo.com/2be679307b2e46e272231527258c0d8d/thumb/1000)
- Hmmm, it sure eats up a lot of memory.


I checked the number of vertices and they were both (9018009, 4), so the number of vertices is not exploding due to the bug.

Oh, okay.
- The cause is not the construction of the graph.
- It's a SET that kept track of visited vertices in the DFS process.
python

```
x = set()
for i in range(9_000_000):
    x.add(i)
```

- ![image](https://gyazo.com/afd0afef705664b82f9b3628c428add9/thumb/1000)
    - [[set is a memory hog]]
    - They're eating 90 bites per entry.
    - I was only concerned about the size 4N graph, but the size N SET was on it by a factor of several dozen.
    - Replace with np.zeros and AC [https://atcoder.jp/contests/abc168/submissions/14647413](https://atcoder.jp/contests/abc168/submissions/14647413)
        - ![image](https://gyazo.com/45ec66aaf39e1d10441d5ff68e6fae69/thumb/1000)

consideration of the causes of defeat
- I assumed the graph was bad because I changed to a pre-built graph implementation and got an MLE.
    - Assumption that the problem lies in the most recent change.
    - In fact, the previous implementation was a TLE, so they just ran out of time before it became an MLE.
- mprof has the ability to produce memory consumption per row. If you had used this early on, you would have realized that the problem is not in the graph construction.
    - I didn't try it because I'm compiling it in NUMBA - so I didn't try it.
- Trial and error process
    - ![image](https://gyazo.com/0caddaabf0befdb5c74626f7f6dae131/thumb/1000)
    - I focused only on the MLE and thought, "This is not a solution at all!" but the memory consumption was properly reduced.
    - The fact that "the fixes have reduced memory consumption, but as a percentage of the total, it's not much" means that "there are other sources of memory consumption besides the ones we're focusing on now."
    - I should have realized at this point and investigated with [[mprof]] to see what was eating memory.

Large data takes too much time, small data consumes too little memory to understand well.
I found just the right one (below).
Since it seems difficult to find out during the contest, it seems important not to write code that is likely to be MLE in the first place
:

```
2510957991
Filename: f_mle.py

Line #    Mem usage    Increment   Line Contents
================================================
    24   79.117 MiB   79.117 MiB   @profile
    25                             def main(N, M, data):
...
    40   79.223 MiB    0.105 MiB       xticks = np.unique(np.concatenate((E, F, C, np.array([-INF, 0, INF]))))
    41   79.223 MiB    0.000 MiB       yticks = np.unique(np.concatenate((A, B, D, np.array([-INF, 0, INF]))))
    42   79.230 MiB    0.008 MiB       width = xticks[1:] - xticks[:-1]
    43   79.230 MiB    0.000 MiB       height = yticks[1:] - yticks[:-1]
    44                             
    45                                 # compress
    46   79.238 MiB    0.008 MiB       A = np.searchsorted(yticks, A)
...
    56                             
    57   79.266 MiB    0.027 MiB       ng_egdes = np.zeros((NUM_VERTEXES, 4), dtype=np.bool_)
    87   79.484 MiB    0.000 MiB       while to_visit:
...
    88   79.484 MiB    0.000 MiB           pos = to_visit.pop()
    89   79.484 MiB    0.004 MiB           y, x = divmod(pos, GRAPH_WIDTH)
    90   79.484 MiB    0.012 MiB           if pos in visited:
...
    96   79.484 MiB    0.000 MiB           total_area += width[x] * height[y]
    97   79.484 MiB    0.125 MiB           visited.add(pos)
    98                                     # plan to visit neighbors
    99   79.484 MiB    0.000 MiB           for i in range(4):
   100   79.484 MiB    0.012 MiB               if not ng_egdes[pos, i]:
   101   79.484 MiB    0.008 MiB                   to_visit.append(pos + direction[i])
   102                                 else:
   103   79.484 MiB    0.000 MiB           print(total_area)
```


[[atcoder]]

---
This page is auto-translated from [/nishio/ABC168 F](https://scrapbox.io/nishio/ABC168 F) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.