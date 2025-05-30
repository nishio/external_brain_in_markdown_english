---
title: "AtCoder Failure List"
---

MLE
- Construct a graph from a given H x W = 10^6 string to TLE or MLE [[PAST5H]].
TLE
- If we take the list of "next vertices to visit" of the whole search and turn it into a TLE set, then AC [[ABC184E]].
- Forgot to put "visited" on Dijkstra implementation [[PAST4J]].
- Preprocessing to speed up, two things to preprocess but only one of them is done, TLE, misunderstanding the computation order and making an ad hoc constant times faster [[PAST4K]].
- One max was inside the loop to calculate the maximum score (TLE) [[ABC175D]].
- Creating a power table in preprocessing: I was doing a ** x and the digits exploded before I got to the remainder / TLE to pow(a, x, MOD) / This is logarithmic order, so when creating the table I should have made it constant order by reusing the previous values [[ARC106]]D
- Constant order, but the constant is 10^9 [[ABC164D]].
- If we replace the prime factorization TLE [[Prime factorize by O(n^(1/4))]] with AC
- Depth-first search is `visit(pos)` when it should be `visit(next)` (you should have noticed this if you tested on hand).
- Implemented depth-first search with recursive function calls, but PyPy is slow to call functions, and the number of times is strictly on the order of 10^6, rewrote to a while loop [[PAST5H]].
- Join strings in a loop, TLE, append to a list, and join at the end [[PAST5H]].
- For repeated multiplication of small matrices, using Numpy is less beneficial because of the large overhead [[ABC189]]E
- AC [[ABC190E]] if you use Dijkstra to change to TLE and BFS even though all sides cost 1.
- TLE by creating a table of 2^16 to remember "what numbers have already appeared" in the digit DP, and only "how many have already appeared" since all kinds of numbers always appear in the digit DP less [[ABC194F]].

RE
- N allocates 10^5 interval DP, 10^10 memory
    - RE: MemoryError  [[MemoryError in AtCoder's Python results in RE]]
        - I should have realized that "we'll never get it done in time with DP." [[AGC048]]B
    - AC: Cumulative sum to collapse the innermost loop and AC [[ABC179D]].
- If you [[depth first search (search algorithm in AI)]] a tree with depth 10 ** 5 in Python, then RE [[AOJ GRL_5_C]] in SegFault.
    - AOJ and my Python are not working, and AtCoder's code test says 10^6 is OK, so it probably depends on the compile options of the processor.

WA
- That I assumed that there was only one connected component that had a size greater than 2. In fact, there is more than one [[ARC107]]C
- Corner case where N=1 in a question about the relationship between multiple things [[ARC106]]C
- I'm setting INF to 10**10 and there are values that exceed [[AGC044A]].
- I compressed the coordinates but accessed them with the original coordinates [[PAST2N]].
- Negative edges in the minimum cost flow library that should not contain negative edges [[PAST3O]].
    - Don't put a negative side in the Dijkstra Law either.
    - [[Do we paint the vertices or the edges?"]] bug that causes a 1 discrepancy [[PAST4M]].
- Continue when the pointer is incremented even though it is a for statement [[ABC178F]].
- I wanted to know if some of the vertices were reachable, but I checked whether the INF was included in the Dijkstra result to see if "all vertices were reachable" [[ABC190E]].
- The initial value of right in a binary search satisfies the condition [[ABC192]]D
- When you get to WA and fix the bug and submit a second time, you do a "fix the bug, lightly speed up" and then put the bug in that speed up. They think the bug isn't fixed and they get confused [[ABC192]]F
- Mathematically there is an O(1) solution, but there is a floating-point number error, I stuck with the O(1) solution, but O(logN) is the correct solution [[ABC191]]D with integer and binary search.

---
This page is auto-translated from [/nishio/AtCoder失敗リスト](https://scrapbox.io/nishio/AtCoder失敗リスト) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.