---
title: "How to avoid TLE with memoized recursive DP"
---

- There are natural problems to implement with recursive calls.
    - For example, a situation in which a dynamic programming method with non-trivial traversal order is implemented by a [[memory recursion]] call
- Python is heavy on numerical operations, so dynamic programming with many operations is easy to TLE.
- With PyPy, function calls are slow, so it's easy to TLE if you overuse recursive calls.
        - [[PyPy function calls are slow]]
- I usually use Numba to compile AOT to speed up the process...
    - Numba does not support recursive calls to functions within functions.
    - Placing it outside the function is not possible with AOT.
    - JIT can be done, but it is compiled during the execution phase, which is not good for speed.
- With Cython, could this be an effective way to compile a function by specifying that it is only called from C?
    - →Fastest at the moment

Use [G - Longest Path](https://atcoder.jp/contests/dp/tasks/dp_g) to find the longest path in a graph as a target problem
- Use the execution speed of test cases 1_17, 1_01 on the AtCoder server for speed comparison
    - 1_01 is the largest one, but I also used 1_17, which is one size smaller, because I couldn't tell the time when it timed out.

Execution time summary
| 1_17 | 1_01 |
| -- | -- | -- | -- |
| 653 ms TLE Code1 Python Rustic Memorized Recursion |
| 422 ms | TLE | Code1 PyPy |
| 735 ms TLE Code2 Python memoizing dict→list |
| 378 ms | 485 ms | Code2 PyPy |
| 434 ms 565 ms Check for computation before calling Code3 Python functions |
| 498 ms | 352 ms | Code3 PyPy |
| 169 ms | 223 ms | Code4 Cython |
| 142 ms 177 ms Code5 Cython memoization array to C array |
| 148 ms 164 ms (best) Code6 Cython End-of-search conditional branching outside of recursion first |
| 1209 ms | 1225 ms | Code7 Numba | JIT |
| 295 ms 368 ms Code8 Python Depth-first search in return order |
| 253 ms | 256 ms | Code8 PyPy |


Code1: Rustic memoization recursion
- Python 653 ms TLE [https://atcoder.jp/contests/dp/submissions/14906600](https://atcoder.jp/contests/dp/submissions/14906600)
- PyPy 422 ms TLE [https://atcoder.jp/contests/dp/submissions/14906630](https://atcoder.jp/contests/dp/submissions/14906630)
python

```
from collections import defaultdict
import sys

sys.setrecursionlimit(10**6)


def solve(N, M, edges):
    longest = {}

    def get_longest(start):
        if start in longest:
            return longest[start]

        next_edges = edges.get(start)
        if not next_edges:
            ret = 0
        else:
            ret = max(get_longest(v) for v in edges[start]) + 1
        longest[start] = ret
        return ret

    return max(get_longest(v) for v in edges)


def main():
    N, M = map(int, input().split())
    edges = defaultdict(set)
    for i in range(M):
        v1, v2 = map(int, input().split())
        edges[v1].add(v2)

    print(solve(N, M, edges))


main()
```


Code2: Version changed to list in case anyone wonders about the use of dict for memoization.
- Python  735 ms TLE  [https://atcoder.jp/contests/dp/submissions/14907532](https://atcoder.jp/contests/dp/submissions/14907532)
- PyPy 378 ms AC 1_01: 485 ms [https://atcoder.jp/contests/dp/submissions/14907612](https://atcoder.jp/contests/dp/submissions/14907612)
- It's possible that PyPy isn't good at accessing dict from this feeling (needs verification).
python

```
def solve(N, M, edges):
    longest = [-1] * (N + 1)
    for i in range(N + 1):
        if not edges[i]:
            longest[i] = 0

    def get_longest(start):
        ret = longest[start]
        if ret != -1:
            return ret

        next_edges = edges.get(start)
        if not next_edges:
            ret = 0
        else:
            ret = max(get_longest(v) for v in edges[start]) + 1
        longest[start] = ret
        return ret

    return max(get_longest(v) for v in edges)
```


Code3 Version to check for computed before function call
- Python 434 ms / 565 ms [https://atcoder.jp/contests/dp/submissions/14916958](https://atcoder.jp/contests/dp/submissions/14916958)
- PyPy 498 ms / 352 ms [https://atcoder.jp/contests/dp/submissions/14907832](https://atcoder.jp/contests/dp/submissions/14907832)
- Reduce the number of function calls by one last call

Code4 Cython
cython

```
cdef get_longest(long start, dict edges, long[:] longest):
    if longest[start] != -1:
        return longest[start]

    cdef list next_edges
    next_edges = edges.get(start)
    if not next_edges:
        ret = 0
    else:
        #ret = max(get_longest(v, edges, longest) for v in edges[start]) + 1
        ret = 0
        for v in edges[start]:
            x = get_longest(v, edges, longest) + 1
            if x > ret:
                ret = x

    longest[start] = ret
    return ret


def solve(N, M, edges):
    cdef array.array longest = pyarray.array('l', [-1] * (N + 1))
    return max(get_longest(v, edges, longest) for v in edges)	 
```

- AC 169 ms / 223 ms [https://atcoder.jp/contests/dp/submissions/14906046](https://atcoder.jp/contests/dp/submissions/14906046)
- I couldn't cdef it as a function within a function, so I took it out.
        - [[Cython does not allow function definitions within functions]]
- Listing access seemed slow, so I changed it to ARAY.
    - This doesn't seem to matter see [[Declaring subscripts as type in Cython is not fast]].
- Generator comprehensions were causing problems, so I rewrote them into a for loop.
        - [[Cython and generator inclusions]]

Put Code5 longest globally as an array in C
- 142 ms / 177 ms
- I wanted a C array, not a list or an array. Related: [[Declaring subscripts as type in Cython is not fast]].
- [https://atcoder.jp/contests/dp/submissions/14913275](https://atcoder.jp/contests/dp/submissions/14913275)

Code6 Conditional branching on whether there is an outgoing edge or not is done first outside of the recursion.
- 148 ms / 164 ms
- [https://atcoder.jp/contests/dp/submissions/14913765](https://atcoder.jp/contests/dp/submissions/14913765)

Numba
- Aside from speed, Numba is a lot harder to get working than Cython, which works without doing anything.
    - `ret = max(get_longest(v) for v in edges[start]) + 1`
        - `The use of yield in a closure is unsupported.`
    - [https://gist.github.com/nishio/dd3013df3e88ef1afb0d41d5980a3882](https://gist.github.com/nishio/dd3013df3e88ef1afb0d41d5980a3882)
        - `Compilation is falling back to object mode WITH looplifting enabled because Function "get_longest" failed type inference due to: non-precise type pyobject`
        - The approach of simply attaching numba.jit does not work, the argument must be an object that allows type inference
- Difficulty in handling graphs in adjacency list format
    - If you make it comfortably in Python, it's dafaultdict(list), but neither dict nor list is appropriate.
    - Since it is variable length, a messy np.array will result in a space of N * M
    - I think it would be best to pass it as a sequence of integers and make it a concatenated list in the Numba world.
        - In this problem, the maximum number of graph edges is fixed, so np.array of that size is allocated.

Code7: Numba JIT
- 1209 ms / 1225 ms [https://atcoder.jp/contests/dp/submissions/14915733](https://atcoder.jp/contests/dp/submissions/14915733)
- It's significantly slower than anything I've ever seen, and I've been through it a lot.
    - But the difference in time between the two problems was 16 ms, about the same as the fastest Cython implementation.
    - This means that the JIT is compiled during the execution phase, which eats up time, but the pre-compiled version is faster.
    - This is also the reason why I usually use Numba with AOT. If you can AOT compile during the compile phase, there is no need to JIT compile during the run phase.
- Numba AOT fails at compile time
    - `Untyped global name 'get_longest': cannot determine Numba type of <class 'function'>`
        - This is because what humans perceive as a recursive call is, for Python, "get a global variable and call it".
            - The type of the retrieved global variable is unknown because the name may be re-bound to another with the same name after the function definition.
            - However, this is inconvenient, so for example, a recursive call could be made possible by a human declaring at compile time that "a call to the same name variable within this function is a call to this function itself", which might be included in a future Numba, I hope!
            - JIT can do it, so why not AOT?
    - So far I haven't found a way to AOT a recursive function that is not tail-recursive with Numba.

Code8: Proposal to process depth-first search in the order of return
- The idea is that you don't have to use recursive calls in the first place, just search the call tree in depth priority and process it on the way back.
python

```
def solve(N, M, edges):
    longest = {}

    stack = [v for v in edges]

    while stack:
        v = stack.pop()
        if v > 0:
            if v in longest:
                continue
            next_edges = edges.get(v)
            stack.append(-v)
            if next_edges:
                stack.extend(next_edges)
        else:
            next_edges = edges.get(-v)
            if not next_edges:
                ret = 0
            else:
                ret = max(longest[x] for x in next_edges) + 1
            longest[-v] = ret

    return max(longest[v] for v in edges)
```

Python 295 ms / 368 ms [https://atcoder.jp/contests/dp/submissions/14916269](https://atcoder.jp/contests/dp/submissions/14916269)
PyPy 253 ms / 256 ms [https://atcoder.jp/contests/dp/submissions/14916290](https://atcoder.jp/contests/dp/submissions/14916290)

---
This page is auto-translated from [/nishio/メモ化再帰DPでTLEを避けるには](https://scrapbox.io/nishio/メモ化再帰DPでTLEを避けるには) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.