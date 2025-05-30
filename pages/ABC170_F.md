---
title: "ABC170_F"
---

[[atcoder]] [F - Pond Skater](https://atcoder.jp/contests/abc170/tasks/abc170_f)  [[ABC170]]
- As explained, position and orientation as vertices [[Dijkstra method]] #Rectangular graph search
- I tried to ignore the explanation, wondering about advancing one step at a time to advance K squares at a cost of one, but no luck.
    - One step in the search will result in a TLE if you advance K squares, so you need to search one square at a time.
- When advancing one square at a time, the vertex must have an orientation because the cost depends on whether the orientation is the same as the orientation of the previous advance.
- It is probably too late to do Dijkstra after making the graph, so do it as you make it.
- The cost will be in 1/K units. With floating point numbers, I'm worried about errors, so I'll have it in two integers, the integer part and the numerator.
- 8 TLE at the stage of the above implementation.
    - First attempt at [[numba]], pre-compile style because of the hassle of blistering speedups.
        - input is of unknown type and cannot be used, so read it and then pass it to the compiled function.
        - Map data is an array of passable bools with guard
            - collision check and in-range check can be combined into one see [[One-dimensional array with guard]].
        - You can't use defaultdict in NUMBA.
            - I tried to use dict, but I get type errors related to get.
            - To begin with, if you use a tuple as a key, it's a type error, so you need to pack it into an integer.
            - Then let's be honest and use an array.
- Usually only a 90 degree turn is needed, but only on the first move, overlooking the possibility of going directly backwards, 2WA
    - I only made the fifth orientation the first time, but maybe I should have just made two 90-degree rotations of the starting state.
Other
- The time consumed during TLE is not helpful because it is terminated before the execution is completed.

-----
According to the explanation, it is the [[Dijkstra method]].
- Since explicitly constructing vertices and edges seems costly, we decided to build them on the fly as needed.

Once the WA returns the number of edges that make up the path instead of the sum of the costs, the WA
- Fix it and TLE [https://atcoder.jp/contests/abc170/submissions/14474187](https://atcoder.jp/contests/abc170/submissions/14474187)
- 3314 ms on PyPy3, about 10% over the time limit (Misunderstanding A)
- I wrapped everything in main and [[line_profiler]] for now, but it's flabby and slow, so I don't know what to do. Let's read other people's code.

python

```
if sys.argv[-1] == 'ONLINE_JUDGE':
    from numba.pycc import CC
    cc = CC('my_module')
    cc.export('main', '(b1[:],i8,i8,i8,i8,i8)')(main)
    cc.compile()
    exit()
from my_module import main
```

[https://atcoder.jp/contests/abc170/submissions/14405996](https://atcoder.jp/contests/abc170/submissions/14405996)
Oh my god. It's pre-compiled by [[numba]].

Right now, we're as far as we can go in a straight line.
- That would mean that a code that takes one step forward would be called hundreds of times that many times, even though it is constrained to an area of less than one million.
- `    49  20156497   22145363.0      1.1     11.3                  nx += dx`
- The commentary said "position and orientation at the apex" but I couldn't figure out why, so I ignored it.

Hard to believe it's only about 10% slower in a situation like this, huh?
- > 3314 ms in PyPy3, exceeding the time limit by 10%. (Misunderstanding A)
- → This one was TLE'd and then censored a bit later.
    - How much it actually needs to shrink is not readily apparent from here.
- I ran 2174 ms on the server with 14.450s on hand.
    - Since it is 7 times slower, does it have to be done in 21 seconds at hand?

Fixed a bug where the distance update on orientation change was wrong, submit, WA.
- Killer01 is 18 seconds in hand and killer02 is 36 seconds, so either way TLE

The reason for the WA was that the distance was now a tuple of two numbers, but the determination of unreachability was still based on a comparison to one number.
- 24 seconds for killer04
- Hmmm, I knew [TLE](https://atcoder.jp/contests/abc170/submissions/14488691)
- killer_03.txt
:

```
7.3          (d, frac), (frm, direction) = heappop(queue) 

8.5          for dir in range(4):
6.0              if dir == direction:

5.3              if nx < 1 or H < nx or ny < 1 or W < ny:

7.7              dp(nx, ny, mapdata[nx - 1][ny - 1])

5.4              if mapdata[nx - 1][ny - 1] == leaf:

5.7              if distances[to] > newdist:
```

Comment out debug printouts that you forgot to erase.
- I had designed it to not output debugging except in debug mode, but it does evaluate arguments.
    - [[Comment out debug printouts]]

I'm running a 4-way direction minus the one I'm facing now, but I might as well shatter this loop.
- One of x,y will no longer have to be updated.
- The cost of internal and external screen checks is also cut in half.
    - (PS: Loop unrolling made it 1/4)

Total execution time went from 80 seconds to 27 seconds. Let's submit.
- Oh, it's WA again.
- Bug: When loop unrolling, forgot to deal with continue and the second half of the loop is not executed.
- Fix and submit, 8 TLEs.
    - I'm thinking maybe replace the tuples with integers... but don't speculate without measurements to speed up the process.
:

```
11.1          (d, frac), (frm, direction) = heappop(queue)
```

    - Hmmm, well, yes...
    - I'm not really motivated to fix this area.

Try [[NUMBA]].

input is said to be of unknown type, so read it outside main and then pass it on.
- `Untyped global name 'input': cannot determine Numba type of <class 'builtin_function_or_method'>`

How do you give them the map? Ah, I see, you make it a one-dimensional array with a guard.
    - [[One-dimensional array with guard]]
- `b1[:]`

Untyped global name 'defaultdict': cannot determine Numba type of <class 'numba.core.ir.UndefinedType'>
- Can't use imported values in globals?
- Import within a function?

`Use of unsupported opcode (IMPORT_NAME) found`
- Hmmm, can't import within a function, I don't want to implement heapq on my own aside from defaultdict.
    - Huh? You're using it, aren't you?
    - heapq can do it.
    - Is defaultdict the only thing wrong?
- [Supported NumPy features — Numba 0.50.0.dev0+236.g64fbf2b-py3.7-linux-x86_64.egg documentation](https://numba.pydata.org/numba-doc/dev/reference/numpysupported.html)

After all, you can't key a tuple.
-like
- `No implementation of function Function(<built-in function setitem>) found for signature:`
- `>>> setitem(DictType[Tuple(UniTuple(int64 x 2), int64),UniTuple(int64 x 2)], Tuple(UniTuple(int64 x 2), Literal[int](0)), none)`
- I think I saw that it's only int and str.
- I fixed that and made the min argument a list.

Key error due to quit defaultdict is not where it happened in the compiled situation, so run in Python mode

Mysterious error `'NoneType' object has no attribute 'args'`.
- It was a bug in the unit.
    - [https://github.com/numba/numba/issues/5896](https://github.com/numba/numba/issues/5896)

It seems that get from dictionary makes the type wrong, so I reimplemented it with a list so that it does not get from a dictionary.
- I'm up to 2WA without TLE.
    - killer_04.txt
    - rand_1000_03.txt
- You answered 1 more than the correct answer on both of these questions.

In the process of speeding up, only a 90-degree turn was made, which meant that the first move was one more answer on the board directly behind.
- AC 881ms [https://atcoder.jp/contests/abc170/submissions/14505545](https://atcoder.jp/contests/abc170/submissions/14505545)

I only made the fifth orientation the first time, but maybe I should have just made two 90-degree rotations of the starting state.
- AC 844 ms [https://atcoder.jp/contests/abc170/submissions/14516254](https://atcoder.jp/contests/abc170/submissions/14516254)

---
This page is auto-translated from [/nishio/ABC170_F](https://scrapbox.io/nishio/ABC170_F) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.