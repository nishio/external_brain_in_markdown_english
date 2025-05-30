---
title: "Solving the Ising model three-body problem with logistic regression"
---

- I want to create an Ising model for input to a quantum annealing machine.
- That is, we want to express it in terms up to the second order of the variable
- The logical expression a and b can be a * b if a and b are {0, 1} variables
- So how do we express a and b and c?
- If we simply set a * b * c, we get a third-order term, right? The problem is this

- Solution 1
    - [Conversion to the Ising model - Quantum Computing Information Site [https://quantum.fixstars.com/introduction_to_quantum_computer/quantum_](https://quantum.fixstars.com/introduction_to_quantum_computer/quantum_) annealing/programming/conversion/]]
    - How to introduce a new variable d
- My solution 1
    - The fact that a and b and c hold means that everything is 1
    - (a + b + c - 3)^2 is 0 only when everything is 1, otherwise it is positive
:

```
[0, 0, 0] 0 9
[1, 0, 0] 0 4
[0, 1, 0] 0 4
[1, 1, 0] 0 1
[0, 0, 1] 0 4
[1, 0, 1] 0 1
[0, 1, 1] 0 1
[1, 1, 1] 1 0
```

    - Only in the last case, the rightmost value (a + b + c - 3)^2 is 0
- My solution 2
    - Solution 1 happened to require a human to come up with a "good replacement method".
    - Can't we get a machine to do this?
    - All input patterns and up to second-order multiplications are used as features, and machine learned by logistic regression in conjunction with correct data.
    - With this size, learning is instantaneous (I think up to about 20 variables can be calculated at a realistic speed).
    - The resulting SCORE is 1.0, so we know it is a linear separation
        - If it is not a linear separation (if you have to add a variable), you will know because the score will not be 1.0
        - I still don't know how to solve the problem in that case.
    - The coefficient at this time
    - `[-1.12247323 -1.12247323 -1.12247323 -1.12247323  7.82630305  7.82630305 -1.12247323  7.82630305 -1.12247323]`
    - That is, 7.8 * (ab + ac + bc) - 1.12 * (a + b + c + a^2 + b^2 + c^2)
:

```
[0, 0, 0, 0, 0, 0, 0, 0, 0] 0 0.0
[1, 0, 0, 1, 0, 0, 0, 0, 0] 0 -2.24494646
[0, 1, 0, 0, 0, 0, 1, 0, 0] 0 -2.24494646
[1, 1, 0, 1, 1, 0, 1, 0, 0] 0 3.33641013
[0, 0, 1, 0, 0, 0, 0, 0, 1] 0 -2.24494646
[1, 0, 1, 1, 0, 1, 0, 0, 1] 0 3.33641013
[0, 1, 1, 0, 0, 0, 1, 1, 1] 0 3.33641013
[1, 1, 1, 1, 1, 1, 1, 1, 1] 1 16.74406977
```

    - You can see that everything is only a gulp bigger when 1.

- What happens when you add four, five, and so on?
    - Much more linear separation

---
This page is auto-translated from [/nishio/ロジスティック回帰でイジングモデルの三体問題を解く](https://scrapbox.io/nishio/ロジスティック回帰でイジングモデルの三体問題を解く) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.