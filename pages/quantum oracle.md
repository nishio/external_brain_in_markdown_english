---
title: "quantum oracle"
---


$U_f: \sum_x|x\rangle \otimes |0\rangle \to \sum_x|x\rangle \otimes |f(x) \rangle$

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>$\otimes$ and $\sum_x$ are often omitted, but explain what they mean.
<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>
The roles of $\otimes$ and $\sum_x$ are very important in the definition of the quantum oracle. Their respective meanings are explained below.

[*** meaning of $\otimes$]
$\otimes$ represents a tensor product. In quantum computation, it is used to represent multiple qubit states together. For example, the states $|x\rangle$ and $|y\rangle$ can be represented as a tensor product $|x\rangle \otimes |y\rangle$. This allows us to treat multiple qubits as a single composite state.

[*** meaning of $\sum_x$]
$\sum_x$ represents the superposition state. In quantum computing, it is common for a qubit to be a superposition of multiple states. For example, if the input state is a superposition of all possible $|x\rangle$, it is represented as $\sum_x |x\rangle$.

# Interpretation of combinations
.
The expression in the definition $U_f:\sum_x |x\rangle \otimes |0\rangle \to \sum_x |x\rangle \otimes |f(x)\rangle$ is interpreted as follows

- $\sum_x |x\rangle \otimes |0\rangle$: Tensor product of all input $|x\rangle$ superpositions and their corresponding auxiliary bits (initially $|0\rangle$).
- $U_f$: Quantum oracle.
- $\sum_x |x\rangle \otimes |f(x)\rangle$: By the action of the oracle, the input $|x\rangle$ remains the same and the auxiliary bit is converted to $|f(x)\rangle$.

This format allows us to express that the oracle's behavior is applied simultaneously to all possible input states.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Can you explain why it is defined this way and why the input x comes out as it is?

<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>
(A few bulleted explanations are listed that miss the point a bit, in case you were wondering, the following explanations were included <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>)
Ensure reversibility: In principle, quantum computation must be reversible. By keeping the input intact, the oracle as a whole is a reversible operation (unitary operation).

---
This page is auto-translated from [/nishio/量子オラクル](https://scrapbox.io/nishio/量子オラクル) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.