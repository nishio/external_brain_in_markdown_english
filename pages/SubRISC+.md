---
title: "SubRISC+"
---

[Tokyo Tech's SubRISC+ CPU Architecture for IoT. 3.8 times more energy efficient - PC Watch](https://pc.watch.impress.co.jp/docs/news/1307882.html)
> The number of instructions is limited to four to reduce size and power consumption.
What are these four? I looked into the topic.
- If you subtract and the result is negative, jump.
- bit AND
- shift
- Memory access (load/store?, details below)
four. Originally known to be Turing-complete with only the first instruction. (OISC: [One-instruction set computer](https://en.wikipedia.org/wiki/One-instruction_set_computer#Subtract_and_branch_if_negative))

[Demonstration of a Compact Power-Saving Processor Suitable for Edge Terminals 3.8 Times More Energy Efficient than Conventional Processors, Paving the Way for Healthcare IoT | Tokyo Tech News | Tokyo Institute of Technology [https://www.titech.ac.jp/news/2021/048954.html](https://www.titech.ac.jp/news/2021/048954.html) by Nishio)
> Here we briefly explain the basics of SubRISC+ to the extent of highlighting our contributions in this paper. SubRISC+ was developed on the basis of a one-instruction set computer (OISC) whose unique instruction is ‘‘subtraction and branch on negative’’ that is capable of realizing any operations and hence is Turing complete. By extending the instruction set architecture (ISA) of this OISC, SubRISC+ handles four instructions (subtraction, bitwise AND, shift, and memory access) that can be flexibly expressed in either 16 bits (for compactness) or 32 bits (to support an immediate value or branch) to improve computing and power efficiency while retaining simplicity with a very limited circuit overhead.
- [https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=9133073](https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=9133073)
- ![image](https://gyazo.com/f67cc8123a482f7b21279f8d29bcae62/thumb/1000)
    - The instruction "jump if A and B are not equal" can be expressed as "A minus B, jump if B is negative, B minus A, jump if A is negative.
    - The bitwise operation not can be expressed by subtracting from the full bit standing -1.

unconditional jump
- ![image](https://gyazo.com/567d984c3e024ff3a3c970f2cdbc82c1/thumb/1000)
- [https://en.wikipedia.org/wiki/One-instruction_set_computer#Subtract_and_branch_if_negative](https://en.wikipedia.org/wiki/One-instruction_set_computer#Subtract_and_branch_if_negative)
- Prepare a POS with positive numbers and a Z with zeros.
- Unconditional jump can be realized by "jump if `Z - POS` is negative
- Execute "`Z = Z - Z`" at the jump destination to set it back to zero.

About Memory Access Instructions
- The paper only mentions "memory access" so I don't know the details.
- Only one? Can it only move in one direction? I thought so, but Mitsunari pointed out that "in x86, load and store together are one mov instruction", so I thought that I could certainly just use the word "memory access" if that was the case.
- Another opinion
    - >  [kazuho](https://twitter.com/kazuho/status/1364492476740820992) I thought it might be a store instruction from a register. In terms of keeping the circuit size down, I think it would be well-balanced to have the two arguments of subneg be memory and register, and the destination be a register, and the store be a separate instruction.
    - Further Postscript
        - [https://twitter.com/kazuho/status/1364537398600880128?s=21](https://twitter.com/kazuho/status/1364537398600880128?s=21)

---
This page is auto-translated from [/nishio/SubRISC+](https://scrapbox.io/nishio/SubRISC+) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.