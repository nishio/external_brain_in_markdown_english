---
title: "Programming Quantum Computers"
---

Publications
- [#1](https://www.slideshare.net/nishio/ss-86734296)
- [#2 [https://www.dropbox.com/s/1iudgckuomizzj5/%E3%82%A4%E3%82%B8%E3%83%B3%E3%82%B0%E3%83%97%E3%83%AD%E3%82%B0%E3%83%A9%E3%83%9F%E3](https://www.dropbox.com/s/1iudgckuomizzj5/%E3%82%A4%E3%82%B8%E3%83%B3%E3%82%B0%E3%83%97%E3%83%AD%E3%82%B0%E3%83%A9%E3%83%9F%E3) %83%B3%E3%82%B02.pdf?dl=0]

We are not here to talk about a quantum computer with a quantum gate system.
- Focus will be on programming with quantum annealing machines.

Quantum annealing is also not explained.
- See here for a very good summary: [Quantum Annealing (Hidetoshi Nishimori)](http://www.stat.phys.titech.ac.jp/~nishimori/QA/q-annealing.html) [cache [https://megalodon.jp/](https://megalodon.jp/) 2017-0821-2211-57/www.stat.phys.titech.ac.jp/~nishimori/QA/q-annealing.html]

Commercial quantum annealing machines are now available from D-wave and others, and programmers who can solve real needs on these machines will be needed in the future.

The process of solving a problem with a quantum computer using quantum annealing:.
- Declaratively describe relationships between binary variables (Ising model)
    - Design the Hamiltonian so that the smaller the Hamiltonian is, the larger the feature you want to obtain.
- A quantum computer can obtain with high probability a solution that minimizes the Hamiltonian of its Ising model.

What most programmers imagine when they hear the word "programming" and what most programmers actually write as part of their work are programs that are executed by a "computer that executes a sequence of instructions in order. This is not the case with programming in languages such as C, Java, and Python, which have been used with this in mind, but rather it leads to confusion.

A few close paradigms
- SAT solver
    - Describes the relationship between binary variables in CNF (Conjunctive normal form, Multiplicative normal form)
    - The SAT solver finds a solution that satisfies the relation (= the number of unsatisfied logical expressions is zero).
        - It can be thought of as "minimizing the number of unsatisfiable logical expressions."
            - (Strictly speaking, it depends on the solver whether it returns a solution with the minimum number of non-satisfiable logical expressions when it is non-satisfiable.)
    - I won't go into detail here see [How SAT/SMT solvers work](https://www.slideshare.net/sakai/satsmt)
- Alloy
    - High-level language to facilitate CNF creation for SAT solvers
    - What is represented as high-level concepts such as "integer" and "one or more exist" on Alloy is converted to CNF and then solved by SAT solver.
- Internal structure of Deep Learning frameworks such as Chainer (computational graphs)
    - Describes relationships between real-valued variables in terms of differentiable functions
        - The relation must be a directed acyclic graph (DAG) structure.
    - Express the "cost function" you want to minimize in terms of a differentiable function derived from the combination of these variables and the training data
    - Deep Learning framework performs automatic differentiation and computes the gradient of the cost function
    - Update each variable in the gradient direction (strictly speaking, there is more ingenuity; see [Optimization algorithm for gradient descent method](https://www.slideshare.net/nishio/ss-66840545))
    - This yields the value of the variable that minimizes the cost function
- Prolog
    - A classic of classics often mentioned when it comes to declarative programming languages
    - First-order predicate logic for relations between variables, and backtracking to find a solution that satisfies the conditions.
    - It doesn't really fit the "programming on a quantum computer" that we are considering here, because it is designed to be solved by backtracking and uses "cut instructions" to control it.

What is the Ising model?
- Turns out that writing a program for a quantum computer is creating an Ising model.
- What is it? How to make it?
- Ising model
- $\mathcal{H} = -\sum_{(ij)\in E} J_{ij} \sigma_i^z \sigma_j^z - \sum_{i\in V} h_i \sigma_i^z$
    - where $\sigma_i^z$ is a binary variable
        - The z in shoulder means spin in the z-axis direction, and we can ignore it because nothing but z will come up in the discussion ahead.
        - One-to-one correspondence with the vertices of the graph
        - It is not important and can be written like this $\mathcal{H} = -\sum_{(ij)\in E} J_{ij} x_i x_j - \sum_{i\in V} h_i x_i$
    - V is a graph vertex and E is a graph edge
        - Weight h for each vertex multiplied by weight J for each side and added together
    - H is for Hamiltonian
        - Energy corresponding to the spin state of the Ising model
        - The quantum annealing machine returns a solution with this small energy with high probability.
            - Same composition as a physical marble rolling to a "low place" with low potential energy.
        - Design the Hamiltonian to correspond to the cost function in an optimization problem, and throw it into a quantum annealing machine to get a solution.
    - The second term is called "magnetic fields," but this is background knowledge that is not necessary for the program.
        - The Ising model was originally a model of ferromagnetism, where the variables take values of -1 and +1, meaning the N and S poles, and if you put the N pole close to a particular vertex, you will apply pressure so that the S pole faces this way.
        - The model for ferromagnetism was that the vertices were arranged on a grid with interactions (=edges) between adjacent vertices, but as you can see from the definition of the formula above, it is a graph, not a grid, and that has been discarded.
        - Because the Ising model formulation of the traveling salesman problem draws a two-dimensional grid in time and space, people who know the two-dimensional Ising model and are not familiar with the quantum computer Ising model (me in the past) misunderstand how the edges of the interrelationships are affixed and get confused.
        - Incidentally, a two-dimensional Boltzmann machine can memorize and recall images. This is almost the same as the two-dimensional Ising model. Since the training time for a full-join Boltzmann machine is on the exponential order, the RBM (Restricted Boltzmann machine), which is restricted to bipartite graphs, is often used in the context of Deep Learning.
            - Note that the training of neural nets is based on some vertex values being given as teacher data and the edge weights being updated, whereas quantum annealing is based on giving the edge weights and finding the vertex values.

- Is this enough knowledge to make an Ising modeling of the traveling salesman problem?
    - Traveling Salesman Problem Tip: Treat as a binary variable "whether or not you are in city i at some step t".
    - Multiply the edge from one city to another at the next time by the weight of the distance
    - If that's all, it falls into the obvious solution of "no movement", so I'd like to add the constraint of "exists only once in each city".
    - In general terms, we want to express the constraint "only one of the N vertices $\sigma_i (0 \le i < N)$ is 1 and the rest are 0
        - This expression can be rewritten as "1 when all N are added" ($\sum_i \sigma_i = 1$)
        - Furthermore, [$ (1 - \sum_i \sigma_i) = 0
            - I used to think here, "How do you add up the vertex values or something?" I used to wonder
        - Square both sides and then expand.
        - $(1 - \sum_i \sigma_i)^2  = 1 - 2 \sum_i \sigma_i + (\sum_i \sigma_i) ^2 = 1 - 2 \sum_i \sigma_i + \sum_i \sum_j  \sigma_i\sigma_j$
        - So once it is deployed, it becomes a normal Hamiltonian.
        - There is a school of thought on whether to set the Hamiltonian binary variables as {-1, +1} or {0, 1}.
            - The {0, 1} type is sometimes called QUBO: Quadratic unconstrained binary optimization. [Wikipedia](https://en.wikipedia.org/wiki/Quadratic_unconstrained_binary_optimization)
            - This Q is not Quantum.
            - It is safe to describe it in either one because it can be easily converted to the other description.
                - ref [Annealing Machines and the Ising Model - Quantum Computing Information Site [https://quantum.fixstars.com/introduction_to_quantum_computer/](https://quantum.fixstars.com/introduction_to_quantum_computer/) quantum_annealing/ising_model/]

- There is a graph mapping problem after being represented by the Ising model.
    - [graph mapping - Quantum Computing Information Site [https://quantum.fixstars.com/introduction_to_quantum_computer/quantum_](https://quantum.fixstars.com/introduction_to_quantum_computer/quantum_) annealing/programming/graph_mapping/]
- This is due to the fact that some parts of the matrix J cannot be non-zero on the actual machine.


reference
- How to represent various NP problems in the Ising model
    - [Ising formulations of many NP problems](https://arxiv.org/abs/1302.5843)
    - That's exactly what I wanted to know!
    - I'll write about each of the issues presented in this paper here in the future, one at a time.
        - [[Ising Programming Club]]


---
This page is auto-translated from [/nishio/量子コンピュータのプログラミング](https://scrapbox.io/nishio/量子コンピュータのプログラミング) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.