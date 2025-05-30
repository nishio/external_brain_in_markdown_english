---
title: "greedy algorithm"
---

>  Algorithm that only "selects a sequence of locally optimal cases using appropriate criteria" ([[chokudai]] [src](https://www.itmedia.co.jp/enterprise/articles/1009/04/news002.html))
- In what order do you make your selections?
- What criteria are appropriate?
- Is the method really the best solution ([[Greed Law Proof Patterns]])?

Regarding the order
- Cases given in question
    - Minimizing the result of repeated operations, etc.
- In the case of matroids, etc., it is obvious because the value you want to increase is from the largest value you want to increase.
- Sort by End of Interval" is non-trivial for interval scheduling
- How should we think in these cases?
- I have a few ideas.
    - From the largest value you want to maximize
        - It's a case where the sum of the gains of each option is maximized, and there's a monotonicity in the addition.
        - [[Greed from those with fewer options.]]
        - In order of strictest to least restrictive
    - From those with the widest sphere of influence
        - What you decide later will not affect the optimal solution of your earlier choice.
        - Sphere of Influence From Outside to Inside Inclusion
    - In decreasing order of decreasing options
        - Choose the one that leaves the most options.
        - The set of choices is inclusive and the outermost one is chosen
    - From the edge of a number line or graph
        - It's easy to think of it this way because it's easy to see, but being on the edge leads to "less choice reduction," "fewer options," etc.


Greed Law on Matroids
    - [[matroid]] (E, F) and given zero or more weights for each element, we want to obtain the element of F with the largest sum of weights
- Repeat "Add to the set of elements already selected in order of increasing weight, if it is an element of F even if it is added to the set of elements already selected".
- [JSC2019 Qualifier E - Card Collector (Matroid) | maspy's HP [https://maspypy.com/atcoder-jsc2019%E4%BA%88%E9%81%B8-e-card-collector-%EF%BC](https://maspypy.com/atcoder-jsc2019%E4%BA%88%E9%81%B8-e-card-collector-%EF%BC) %88%E3%83%9E%E3%83%88%E3%83%AD%E3%82%A4%E3%83%89%EF%BC%89]

- [[Kruskal method]]
- The problem of constructing a minimum global tree by selecting edges so as not to create a closed path.
- Repeat "choose if it doesn't make a closed path with an already chosen edge" in order of decreasing side length.
- Greedy Law on Matroids Applied to Graphical Matroids

- [[Interval Scheduling]]
- The problem of selecting as many sections as possible so that there are no common parts.
- Repeat "If there is nothing in common with the already selected one, select it" in the order of the end of the interval.
- Segments with an interval beginning before the chosen "end of the interval" cannot be chosen in the future
    - That is, the one that leaves the most options to choose the one that ends the interval the fastest.
    - [[Replacement does not make it worse.]]
        - [[Algorithms and Data Structures]] p.112
    - [[Section is not a matroid.]]


[[ABC076B]]
- [https://atcoder.jp/contests/abc076/tasks/abc076_b](https://atcoder.jp/contests/abc076/tasks/abc076_b)
- Perform one of two operations on the number 1. We want the minimum value of the result of N operations.
- Both of the two operations have the property "if the number before the operation is small, the result is also small".
- Just choose the one with the smaller result for each operation.
        - [[The better the present, the better the future]]
        - monotonicity
- Repeat "choose the one with the smaller result of the operation" in the order of time axis.

Coin Issues
- I want to pay a certain amount in coins and minimize the number of coins
- The amount of the coin is a multiple of the coin in front of it, a property that
- Pay as much as you can in big coins.
- Repeat "pay as much as you can" in order of the size of the coins
- If coin A is a multiple of coin B, the only way to pay the shortfall in amount due to a reduction of one coin A by B is to use two or more Bs, which always increases the number of coins
    - If it is not a multiple, for example, 5,4,1 to pay 8, there is a pattern that 5 is reduced by 1, 1 is also reduced by 3, and 4 can be paid with 2 cards, -2 cards, and so on
    - The coin amounts are multiples of each other, so there is zero "too much" and you don't have to worry about the smaller number of coins
    - Cases like 15,5,3,1 are the same in 9.

[[POJ3617]]
- Take one character from the beginning or end of string S and add it to T. I want T to be the smallest in dictionary order.
- The lexical order criterion has the property that if the first letter is smaller, it is smaller in lexical order, regardless of what comes after it.
- Prepare S' with S inverted.
- Repeat "Select the smallest of S and S' in lexicographic order and take the first letter" in chronological order.

[[POJ3069]]
- There are N points on a number line. We want to select some of them so that all the points are included in the "range within distance R from the selected point". Minimize the number of points to be chosen.
- Repeat the process of "choosing the rightmost point on the number line that can cover the points not covered by the points already chosen" from left to right.

- [[Dijkstra method]]
- The problem of finding the shortest path
- Initialize the visited vertex with a single starting point
- Repeat "Select vertices that have not been visited and can be reached by a single edge from the visited vertices in order of shortest distance from the starting vertex.
- Assuming that the distance between the sides is positive
- Since the distance of the edge is positive, "V", which is the shortest distance from the starting point among the vertices that are unvisited and reachable by one edge from the visited vertex, has no shortest path through the other unreachable vertices, so

[[AGC009A]]
- Given two number sequences A and B, pressing the i-th button increments A0 to Ai. We want Ai to be a multiple of Bi for all i. Minimize the number of button presses.
- Repeat "press the minimum number of times that Ai and Bi satisfy the condition" in order of increasing i
- Inclusion of the sphere of influence, the small one does not affect the large one because the large one with i encompasses the small one

Knapsack-like problem
- There are several kinds of goods, given their value and number of pieces, there is a knapsack that holds N pieces of goods, maximize the value of the goods in the knapsack.
- Unlike the so-called knapsack problem, it is not "the weight of one undividable item" but "the number of items", so the fact that it can be divided is important.
- Repeat "choose as many as you can" in order of value.

[https://www.itmedia.co.jp/enterprise/articles/1009/04/news002_3.html](https://www.itmedia.co.jp/enterprise/articles/1009/04/news002_3.html)
- Given two vertex sets A, B and the rank of the vertices. Determine if there is a bipartite graph that satisfies the conditions.
- Repeat "select and connect the vertex with the highest remaining degree from B" in the appropriate order of A
- Actions that do not reduce options the most

[[ARC111]]C
- A person is holding a piece of luggage, I want to exchange the luggage so that it is held by the original owner. The maximum weight a person can hold differs, and if a person holds a heavy item, it cannot be exchanged afterwards.
- Repeat "exchange the luggage for the original owner" in order of weight.
- You can always "trade for the original owner."
    - It might put the recipient out of action, but it doesn't matter because he already has the original package.
    - What the sender receives is always "lighter than what he had."
    - Any other order could cause "what comes back is too heavy".


Sort by difference between two choices
- Ai/Bi and K A's are chosen for the gain of choice A/B, respectively, and I want to maximize the gain.
- Repeat "Select K A's" in the order of Ai-Bi.
- variant: [[ABC187]]D
    - Ai+Bi with "choose A", -Ai without, want to make the sum positive with the smallest choice
    - Repeat "Choose A" until the sum is positive in the order of the greater of 2*Ai+Bi.

[[ARC110C]]
- Sort the given columns in ascending order
- Bring the smallest value to the top, the rest will ignore that value [Same shape issue, one size smaller
- Repeat "bring to top" in order of decreasing value

Minimizing the difference between pairs of numbers
- I have an even number of numbers, I want to pair them 2 by 2 and minimize the difference.
- Repeat "pair with the next number" in order of decreasing value
- Pairing the smallest number with any number other than the next will always result in a loss
- Removing the pair would result in [Same shape issue, one size smaller


[[AGC049B]]
- Given a sequence S,T of 0/1, for S you can either shift one 1 to the left or set two 1s in a row to 0. Match T with the least number of moves.
- Repeat "If there is an unresolved 1 to the left of yourself in T, shift it, if not, delete it" in order from the front of S

[[ABC103D]]
- Given a number of intervals, given a point, all the intervals including that point will be removed. I want to remove all intervals with the minimum number of points
- Repeat "Select the section immediately before the end" in the order of the earliest end of the section.
- This is the option that has the greatest impact on the other sections of the method of removing "the section with the earliest termination"

[[ABC023D]]
- Given a positive number sequence H,S, where subscript i is chosen Ki th and we want to minimize the maximum of H+SK, construct K
- Not in the order of H or S.
- Introduce an upper bound X on the maximum value and make it a decision problem to see if it can be realized.
- Repeat "selection" in decreasing order of (X-H)/S
- Implication: select in order of decreasing number of options not exceeding X

- [[Maximize the sum ratio]]
- I have a positive sequence Ai,Bi, choose K subscripts, and I want to maximize the ratio of the sums of each of AB
- If the problem is to determine whether the ratio is greater than or equal to X, the transformation of the equation leads to a simple sum of (Bi-XAi), which can be maximized by the greedy method of choosing from the larger values.
- Repeat "Select" in order of increasing (Bi-XAi)



---
Links to many issues
[https://www.yasu-p.com/entry/python-algorithm-2-2](https://www.yasu-p.com/entry/python-algorithm-2-2)

POJ3253
- Ant book p.49
- It's a little complicated.

- [[unit time job scheduling problem]]
- [https://archive.org/search.php?query=http%3A%2F%2Ftopcoder.g.hatena.ne.jp%2Fspaghetti_source%2F20121103%2F1351911603](https://archive.org/search.php?query=http%3A%2F%2Ftopcoder.g.hatena.ne.jp%2Fspaghetti_source%2F20121103%2F1351911603)


[AtCoder D - The real fight (ARC019) | maspy's HP [https://maspypy.com/atcoder-d-%E3%81%BB%E3%82%93%E3%81%A8%E3%81%86%E3%81%AE%E3%81%](https://maspypy.com/atcoder-d-%E3%81%BB%E3%82%93%E3%81%A8%E3%81%86%E3%81%AE%E3%81%) 9F%E3%81%9F%E3%81%8B%E3%81%84%EF%BC%88arc019%EF%BC%89]
    - [[random selection + greed]]

[AtCoder Participation Comments 2020/04/19:ABC 163 | maspy's HP](https://maspypy.com/atcoder-%E5%8F%82%E5%8A%A0%E6%84%9F%E6%83%B3-2020-04-13abc-163)
- The justification for the greed law is narrowed down to two options in a validating manner.

[AtCoder Participation Comments 2019/02/16:ABC 155 | maspy's website](https://maspypy.com/atcoder-%E5%8F%82%E5%8A%A0%E6%84%9F%E6%83%B3-2019-02-16abc-155#toc4)
- I solved it with a digit DP, but greed can do it too.

[[ABC171 F]]
- [AtCoder ABC 171 F - Strivore (blue, 600 points) - Kenchon's Competitive Pro Devotion Record](https://drken1215.hatenablog.com/entry/2020/06/27/125500)

Problems for which the greedy method can lead to an optimal solution and those for which it cannot
- Coins that are and are not optimal for the "spend as much as you can from a large amount of coins" coin problem.
    - 1,4,5 no.
    - [[matroid]]
    - [[discrete convexity]]
- [Convex structure of matroids - Kenchon's record of competitive professional diligence](https://drken1215.hatenablog.com/entry/20121212/1355280288)

- Fundamentals of Discrete Optimization Part 5: Matroids and Global Trees of Graphs
    - [http://dopal.cs.uec.ac.jp/okamotoy/lect/2015/matroid/handout05.pdf](http://dopal.cs.uec.ac.jp/okamotoy/lect/2015/matroid/handout05.pdf)
- [https://www.jaist.ac.jp/~uehara/course/2014/i431/pdf/04greedy.pdf](https://www.jaist.ac.jp/~uehara/course/2014/i431/pdf/04greedy.pdf)
- [http://agent.inf.kyushu-u.ac.jp/~yokoo/lecture/DA2_5A.pdf](http://agent.inf.kyushu-u.ac.jp/~yokoo/lecture/DA2_5A.pdf)
- [http://www.iip.ist.i.kyoto-u.ac.jp/member/keisuke/resources/sec16_2.pdf](http://www.iip.ist.i.kyoto-u.ac.jp/member/keisuke/resources/sec16_2.pdf)
- Theory and Algorithms for Discrete Convex Analysis
    - [http://www.orsj.or.jp/archive2/or58-06/or58_6_332.pdf](http://www.orsj.or.jp/archive2/or58-06/or58_6_332.pdf)

---
This page is auto-translated from [/nishio/貪欲法](https://scrapbox.io/nishio/貪欲法) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.