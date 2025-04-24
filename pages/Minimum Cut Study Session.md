---
title: "Minimum Cut Study Session"
---

2021-03-19 Cybozu Labs Study Session
Explain "solving by attributing to a minimum cut problem" that can be used to solve certain optimization problems.

Simple optimization problem
- There are n two choices.
- You get 100 yen for each choice you make.
- But it costs Ci yen to choose.
- What are the choices that maximize profit?

answer
- Profit 100 - Choose the one with positive Ci

Simple optimization problem 2
- There are n two choices.
- You get 100 yen for each choice you make.
- But it costs Ci yen to choose.
- If you choose M alternatives what choice maximizes profit?

answer
- Sort and take M pieces from the one with the largest profit.

A problem one step further.
- There are N choices of two options (N=20)
- You get 100 yen for each choice you make.
- But it costs Ci yen to choose.
- If one chooses option i and does not choose option j, it costs an additional Dij.
    - M non-zero costs (M=100).
- What are the choices that maximize profit?

answer
- Search all $2^N$ streets
- $2^{20} = 1048576 \approx 10^6$ to calculate Dij * 100 so about $10^8$ times
- Python3 `11.3 s ± 173 ms per loop (mean ± std. dev. of 7 runs, 1 loop each)`
- PyPy3 `1.1 s ± 37 ms per loop (mean ± std. dev. of 7 runs, 1 loop each)`
- [spec](https://gyazo.com/ebcccd3c36cf60a0b1ecac5b39a598ed)


problem to be solved this time
- There are N choices of two options (N=100) ←🤔
- You get 100 yen for each choice you make.
- But it costs Ci yen to choose.
- If one chooses option i and does not choose option j, there is an additional Dij cost
    - Non-zero cost is M (M=100)
- What are the choices that maximize profit?

What if it's a full search?
- $2^{100} \approx 10^{30}$
- Even if we use a machine that can calculate $10^{10}$ times in 1 second, it would take $3^times 10^{12}$ years.

answer
- Attribute to the minimum cut problem, transform it into a maximum flow problem with the maximum flow minimum cut theorem, and solve it with the Dinic algorithm.
- Quite fast.
- When N=M=100, it was less than one millisecond.
    - Time repeated 1000 times
    - Python3 `858 ms ± 222 ms per loop (mean ± std. dev. of 5 runs, 1000 loop each)`
    - PyPy3 `214 ms ± 139 ms per loop (mean ± std. dev. of 7 runs, 1000 loop each)`
- N=M=10000, but about 0.2 seconds.
    - Python3 `243 ms ± 40 ms per loop (mean ± std. dev. of 5 runs, 1 loop each)`
    - PyPy3 `114 ms ± 45 ms per loop (mean ± std. dev. of 7 runs, 1 loop each)`
- N=M=100000, PyPy would be about 1-2 seconds.
    - PyPy3 `1.4 s ± 172 ms per loop (mean ± std. dev. of 7 runs, 1 loop each)`

What is Cutting?
- > The bipartition (S, T) of a graph G(V, E) at vertex V is called a cut.
- ![image](https://gyazo.com/43aabb7d6bc127d28e6a30af2587f230/thumb/1000)
- Just split the "set of vertices" in two.
    - As a physical image, "painting in two colors" fits.
- The word "cut" is a confusing word to think of "cutting the graph in two".
    - I don't care what side you're on.
    - Here's another cut.
        - ![image](https://gyazo.com/bef1cd4eb2267d237c915778a1bbcedb/thumb/1000)
- Some descriptions in the world say "what about flow" at this point, but I don't care here because it is fine to think about flow in the later phase of "mapping the minimum cut to the maximum flow".
    - Thinking about flow at this stage is also confusing. Since there is no flow corresponding to the above cuts.

What is the minimum cut problem?
- (This time we are only talking about directed graphs.)
- Given a cut $(S, T)] of a directed graph [$ G = (V, E)], the edge [$ (u, v) \in E$ of G that is $u \in S, v \in T$ is called a cut edge.
- ![image](https://gyazo.com/359c47fe470936b043715e30d037e816/thumb/1000)
- The sum of the weights of the cut edges is called the size of the cut, and the cut with the smallest size is called the smallest cut.
- Often it is convenient to consider "vertex s that always goes into S" and "vertex t that always goes into T." A cut such that s and t are so is sometimes called an "s-t cut.
- Q: Is an edge that has a T at the base and an S at the end not a cut edge?
    - A: Good question, confirm understanding on next slide

Confirm understanding of minimum cuts
- What would be the s-t minimum cut on this graph?
- ![image](https://gyazo.com/168b48ffc582651499fb4f302efeb396/thumb/1000)
- (Note: In the original figure, vertices were written in uppercase, but this was changed to lowercase to distinguish between vertex set S and vertex s.)


answer
- $a \in T, b \in S$ when cut size is minimum at 3
- ![image](https://gyazo.com/995e58aae1d3cb623ed98988226a491e/thumb/1000)
- It's easy to get confused when you think of a cut as "cutting the graph" and not cutting the "middle 5 edges".
    - The size of the cut is irrelevant because the edge is such that the root is a T and the tip is an S
- There are four ways to paint the vertices with two colors since s and t are fixed.
    - $a \in S, b \in T$ when 15
        - ![image](https://gyazo.com/7fc7471991992121307a80ca0a58899e/thumb/1000)
    - 6 when both are S or both are T.
    - So 3 is the minimum
    - [[Cutting the smallest cut is not "cutting an edge".]]
    - [[Cut = Two-color painting of apex]]

- [[Comes down to the smallest cut.]]
- reprint
    - > Transformed into a maximum flow problem by the maximum flow-minimum cut theorem, attributed to the minimum cut problem and solved by the Dinic algorithm
- I just finished explaining what a "minimum cut problem is."
- Next, I will explain how the following problem can be attributed to a minimum cut problem
    - > There are N choices of two options (N=100) ←🤔
    - > You get 100 yen for each choice you make.
    - > But it costs Ci yen to choose.
    - > If one chooses option i and does not choose option j, there is an additional cost of Dij. M non-zero costs (M=100)
    - > What choice maximizes profit?
- Want to maximize profit = minimize cost
    - Cost can be minimized with the smallest cut if cost is the weight of the edge
- If "choose option i" is set to "put vertex i into S
    - What is "Choice and Cost Ci"?
        - Subtract an edge of weight Ci from vertex i to vertex t
        - ![image](https://gyazo.com/524e99154d4027721faf1f2af574617a/thumb/1000)

    - What is "Reward 100 if you choose"?
        - Since the reward is negative cost, subtract the edge of weight -100 from vertex i to vertex t
        - ![image](https://gyazo.com/b2661c356bfd0ec6c234db5bde167683/thumb/1000)
        - (Negative sides will need to be removed later, but don't think about that now.)
    - If you pick i and don't pick j, cost Dij."
        - Subtract an edge of weight Dij from vertex i to vertex j
        - ![image](https://gyazo.com/ccff2a4b41fcc2c2762313d0efd2635a/thumb/1000)
- Find the minimum cut in this graph and you will get the answer you want to get

concrete example
- There are three two-option choices a, b, and c
- There is a reward of 100 for choosing
- Each choice costs 10,70,150.
- If you don't choose c when you choose a, you'll have to pay an additional cost of 40.
- Graph to be constructed
    - ![image](https://gyazo.com/33e4fbbd0f7a27cc4e6044c398f4be2b/thumb/1000)
- Q: "Is it okay to have the s separated? Is that the obvious place to make the smallest cut?"
    - A: There is an edge with negative weight, so that is not necessarily the minimum solution.
    - This confusion is caused by confusing "cut" with "split the graph in two".
    - From the next slide, convert this minimum cut problem to a maximum flow problem. In the process, s is connected and becomes a graph suitable for considering flow

What's next?
- reprint
    - > Transformed into a maximum flow problem by the maximum flow-minimum cut theorem, attributed to the minimum cut problem and solved by the Dinic algorithm
- I was able to attribute it to the minimum cut issue.
- Next convert to maximum flow

maximum flow problem
- Given a graph $G=(V,E)$ with non-negative edge weights
    - This weight is called "capacity" in the context of flow
- Consider the flow between two vertices s, t of this graph
    - Image of water flowing from s to t
    - How much will flow when the maximum flow? is the maximum flow problem
    - ![image](https://gyazo.com/8758e36faec9134793d689cb4a264558/thumb/1000)
- A flow on G is a weighted graph $(V,F)$, where:.
    - The weight of each side does not exceed the capacity at G: $F_{ij} \le E_{ij}$
    - The incoming and outgoing flows match for vertex i except s,t: $\sum_j F_{ji} = \sum_j F_{ij}$

maximum flow minimum cut theorem
- It is known that the size of the s-t minimum cut of a graph with non-negative edge weights and the flow rate of the maximum flow from s to t coincide
- No proof this time.
    - see [Akiyoshi Shioura Mathematical Programming 8th](http://www.dais.is.tohoku.ac.jp/~shioura/teaching/mp08/mp08-08.pdf)
- rough image
    - ![image](https://gyazo.com/c8d058721468b3e5e979c138c46398d0/thumb/1000)
    - Considering the graph (residual network) of the maximum flow F from s to t reduced from the capacity of G, this is always split into two or more connected components
    - If not, it would further increase the flow and contradict the assumption (e in the figure).
    - The "divide the graph vertex into two" is a cut, and maximizing the flow results in a bottleneck in the area of the smallest cut.

Negative side removal
- Convert a minimum cut problem to a maximum flow problem and solve it.
- Negative edges need to be removed because the capacity of the edges must be non-negative in the maximum flow problem
- If we focus on a vertex i, it can either be in S or in T
    - ![image](https://gyazo.com/7b1dc6c9b05f46514a98a792ac9c34c1/thumb/1000)
- So make it so that the same amount of additional cost c is charged when you enter S and when you enter T
    - ![image](https://gyazo.com/d492c8b93c3c6a738e72feb7f74f30a1/thumb/1000)
    - Now the negative side disappears.
    - The minimum cut size of the modified graph will increase by c
    - Keep track of the sum (offset) of the values added in the process of negative side removal, and subtract it after the answer is obtained.
- example
    - ![image](https://gyazo.com/070b43a35881de73f82f59ef008cf290/thumb/1000)
    - Negative side removal
        - ![image](https://gyazo.com/3ac01c8a8e471f03a7c9d8d987883e90/thumb/1000)
    - Minimum cut is -80
        - ![image](https://gyazo.com/c25e7a10f970b57f811c98482084fd7f/thumb/1000)

- (Negative edge removal between free vertices is described below.)

[[Dinic]] Algorithm
- Efficient algorithm for finding the maximum flow of a graph
- A slightly modified version of the classic Ford-Fulkerson
    - (Although, Dinic is also 1970, so it is a classic.)
- I won't explain in detail this time. see: [Slide by Guo Zhixian](https://www.slideshare.net/KuoE0/acmicpc-dinics-algorithm)
    - If you put in a directed graph with non-negative edge weights and a start point s end point t, you get an s-t max flow
    - This matches the size of the smallest cut
- After calculating the maximum flow, we can search on the residual network we have inside to find the vertices that can be reached from each vertex's s. That will be the S of the minimum cut.

Dinic's computational complexity
- Dinic's computational complexity is assumed to be O(V^2E)
- But it's a search-based method, so even 10^4 vertices and 10^4 edges are not always calculated 10^12 times
    - When N=M=10000 in the previous problem, the graph has 10002 vertices and 20000 edges
    - This could be calculated in 114 ms.
- Up to what size problem can you solve?
- Tried with N=10000 fixed and increasing M (horizontal axis M, vertical axis ms) [data](https://gist.github.com/nishio/b6fb56b7a4ffe179d3e8ecd9336e01d8).
    - ![image](https://gyazo.com/d8cbd60649437758dbe21e1879792551/thumb/1000)
    - Almost linear (a little worse?) in this range.
    - This is fixed V and increasing E, so it's linear in theory.
- Move N and observe under the condition N=M [data](https://gist.github.com/nishio/9a2c26ca27dc3a6f7387a333011ed1f3)
    - ![image](https://gyazo.com/d1c993d547f697e4c28d1e7493af4eef/thumb/1000)
    - N^3 in terms of computational complexity, but the actual measurement appears to be linear.
    - Perhaps "the graph produced from this optimization problem" has "features that are convenient for Dinic".
    - [[Dinic speed]] : When the edge weights are integers, the computational complexity goes down under various conditions.
    - In this experiment, each cost is a "random integer between 1 and 200" so the edge weights are integer and capped
    - In this case, the upper bound is C. $O(CV^{2/3}E)$


application
- Constraints of type "When i is chosen, j must be chosen
    - Just make i→j a large enough cost.
    - ![image](https://gyazo.com/a36987a1132e4c91363ac279fc885823/thumb/1000)
- and: "If you chose i, you must choose j and k."
    - ![image](https://gyazo.com/1a4707c9a418f24645f793d329639594/thumb/1000)
- OR: "If i or j is chosen, then k must be chosen."
    - ![image](https://gyazo.com/931213f2a1843b8e75140af39990962e/thumb/1000)

[[Project Selection Problem]]
- With the knowledge so far, you can solve a type of problem called Project Selection Problem.
    - There are N projects.
        - Doing project i yields income [$ r_i
    - There are m machines.
        - Buying machine j costs [$ c_j
    - In order to do a project, you have to buy the machinery needed for that project.
    - Which project should I choose to maximize profit = revenue - cost?
- ![image](https://gyazo.com/052e99dda764a20363b0fea423f5cf79/thumb/1000)


Application Continued
- not
    - When you pick i, don't pick j."
    - This is generally not always possible.
    - Express choosing i by putting i in S and expressing choosing j by putting j in T
    - This way we can express the above constraints, but we need to decide in advance "which way it will go when selected".
    - At this time, the above constraint can only be applied between "the vertex that enters S when selected" and "the vertex that enters T when selected
        - In a word: "bipartite graph."
    - Adjacency of a single row or two-dimensional square
        - Just alternate S and T.
        - Use this for problems where painting squares and adjacent squares incur costs.

More than two choices
- be made
- Example of three choices
    - ![image](https://gyazo.com/25b91d664ab124974644d9b1ddcff4e2/thumb/1000)
- Similarly, N choices can be represented by arranging N-1 vertices
- Similarly, for a real-valued variable, "if i is greater than or equal to x, then j must be greater than or equal to y" can be done
    - ![image](https://gyazo.com/72ecfe85ce3e414d2a0e00f5c3fd4b7a/thumb/1000)

Negative edge removal between free vertices
- How do we remove these types of negative sides?
    - ![image](https://gyazo.com/10039fd078d02c20d1146ff98eec2658/thumb/1000)
- Maybe we can't keep this up.
- Change j to the vertex j' of "T when chosen".
- ![image](https://gyazo.com/4cc6a94cbf16b1eeeac29997edad9df8/thumb/1000)

- It is even easier if the infinity edge is facing the opposite way.
    - ![image](https://gyazo.com/0e17acaac7437f7a2b7e5cf93268f9a8/thumb/1000)
    - Since there is no problem with a larger "sufficiently large weight"
    - ![image](https://gyazo.com/d6313aacf7e7bf0b63ab598d7a99d51e/thumb/1000)


What I don't know yet
- Can we have and of the form "if i and j are S, then k is also S"?
- Can we have an or of the form "if i is S, then j or k is S"?
- Can't we solve this by sandwiching an intermediate layer in the same way we used to represent the n choices?
- For example, in the case where there are two choices (0/1) for N objects (A, B), the pattern is "cost c if Ai=1 and Bi=0", "cost d if Ai=1 and Bi=1", and "cost e if Ai=0
    - I'm having a hard time figuring out how to realize AND if I think these are the two choices.
    - If you treat it as one of the three options, it's a straightforward form of cost for each option.
- Perhaps the problem lies in the fact that we, who are accustomed to expressing problems in logical expressions, first express them in logical expressions and then try to convert them to minimum cuts.
    - I don't think there is a conversion from a general logical expression to a minimum cut.
    - Rather, the problem needs to be expressed in the smallest possible cut from the beginning.
    - This is similar to the composition of "thinking of a logical equation and then turning it into a neural net" and "thinking of a logical equation and then turning it into a Hamiltonian".

---
This page is auto-translated from [/nishio/最小カット勉強会](https://scrapbox.io/nishio/最小カット勉強会) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.