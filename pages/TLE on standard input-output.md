---
title: "TLE on standard input/output"
---

The first time I implemented a segmented tree, I got a TLE.
I thought, "What's wrong? It doesn't look much different from [the AC person's code](https://atcoder.jp/contests/abc170/submissions/14338427)..." and compared the person's code with [[line_profiler]] on my hand. Profiler] and compared them, and found that the problem was standard input/output.

Below is a formatted version of the profile results. The numbers are the number of executions, total execution time, execution time per execution (usec), and percentage of the total.
:

```
200000    2601965.0     13.0     15.5
C, D = [int(x) for x in input().split()]
```

No, no, no, you're spending 15% of your time on one line of data loading!

What's the code for AC people?
:

```
200000     374839.0      1.9      1.3
c, d = map(int, input().split())
```

What? Is it so different if it's a MAP or a closed list package?

I'll rewrite mine on map.
:

```
200000    2244127.0     11.2     14.2
C, D = map(int, input().split())
```

Mine is 11.2 usec and the AC guy's is 1.9 usec, even though they are the exact same code, what does that mean?

Compare the output part as it pings here.
I used to print every time in a loop, AC's were compiled in a list and printed after the loop was over.
I'll try to copy and modify it. It's not getting faster just for this output part. In fact, it has slowed down slightly.
:

```
before
200000     383636.0      1.9      2.4
print(segtree_node[1])

after
200000     222367.0      1.1      1.4
answers[t] = segtree_node[1]

     1     176312.0 176312.0      1.1
print(*answers, sep="\n")
```


And as a result of this modification, the input portion was nearly doubled from 11.2 usec to 5.7 usec.
:

```
200000    1135919.0      5.7      7.0
C, D = map(int, input().split())
```

Now my TLE'd code is AC. Seriously....

This is still more than twice as slow as the 1.9 of the AC people. I wonder what else is affecting this... Mystery...

Ah, mystery solved.
python

```
import sys
input = sys.stdin.buffer.readline
```


[8 minor processing speed differences in Python that you should know - kumilog.net](https://www.kumilog.net/entry/python-speed-comp#input-%E3%81%A8-sysstdinreadline)
>  Surprisingly, the difference is more than 10 times. In competition programming, where the execution time limit is often 2 sec and the number of input data is 106, a difference of 0.3~0.4 sec is quite significant.

:

```
200000     311399.0      1.6     10.9
C, D = map(int, input().split())
```

and they all lived happily ever after (traditional ending to stories)

memo
- sys.stdin.buffer.readline reads as a sequence of bytes
- line break at the end of a line

---
This page is auto-translated from [/nishio/標準入出力でTLE](https://scrapbox.io/nishio/標準入出力でTLE) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.