---
title: "AGC029B"
---

[B - Powers of two](https://atcoder.jp/contests/agc029/tasks/agc029_b)
- ![image](https://gyazo.com/080d6b0ddcfd467e67ccc6894b6b8155/thumb/1000)
- Thoughts.
    - Enumerate the pairs whose sum is 2 bekiest and select them so that there are no duplicate vertices.
    - But if you do it naively, "check if the sum is 2 beki for each pair" is 10^10 and impossible.
    - When two numbers add up to 2 Beki, is there any other characteristic?
    - If I can make a frequency table, I can do it in about 10^7.
    - How do you maximize pairs after the graph is created?
        - There can be vertices with the same value
        - Not 1,1,3 or a two-part graph.
        - Oh, like a coating or something of that nature?
    - Google (i.e. to search for on the WWW using the Google search engine)
        - Maximum matching for bipartite graphs is well-known, but apparently there are polynomial-time algorithms for general graphs as well.
        - But O(N^4)...
        - Can you say the upper limit on the number of vertices that can participate in a 2-vekiable graph?
            - And you can chop up anything that isn't consolidated.
            - Oh, no, there's "all one" or something.
    - If there are three 2-veki numbers e.g. 8, there can be a pair 8-8 with itself
        - Can these areas be removed first?
        - No. You have more pieces if you don't make 8-8 when you have 8,8,24,56.
    - The same vertex can be used over and over again, and it's self-explanatory, so don't think of it as a general matching.
    - This is probably best taken from a point with rank one.
        - Is there ever a point with a rank of 1 that does not exist? Yes, or a case where there are four 1's.
        - It should be "the point where there is only one paired point, including yourself."
    - When a number x is paired with another number $2^a-x, 2^b-x$ (a<b)
        - $(2^a-x) + (2^b-x) = 2^a+2^b-2x = (2^{b-a} + 1)(2^a) - 2x$
        - Is it a leap to conclude that 2x=2^a when this is a pair?
        - When x is odd, the pair of values is also odd, and when x is even, the pair of values is also even, so divide by 2 until x is odd, and consider the case where x is odd
        - Dividing the right-hand side by 2, we get $(2^{b-a} + 1)(2^{a-1}) - x$.
            - For a>1 this would be an odd number.
                - The only odd number allowed as 2^c divided by 2 is 1
                - hmm
- Official Explanation
    - This policy of "starting from a point with a rank of 1" is a good one.
        - I haven't found an efficient way to find this out.
        - [[On the contrary, think from the larger side.]]
        - It is essential that the vertex with the largest value has only one pair of values in this problem condition
        - [[Fill in the maximum matching on the graph from the end.]]
- problem partitioning
        - [[Maximum matching]]

---
This page is auto-translated from [/nishio/AGC029B](https://scrapbox.io/nishio/AGC029B) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.