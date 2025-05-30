---
title: "2-state, 3-color Turing machine"
---

[http://mathworld.wolfram.com/TuringMachine.html](http://mathworld.wolfram.com/TuringMachine.html)
The figure shown here is a 3-state, 2-color [[Turing machine]].

[20-year-old student proves "Mr. Wolfram's Turing Machine" | WIRED.com [https://wired.jp/2007/10/26/%e3%80%8c%e3%82%a6%e3%83%ab%e3%83%95%e3%83%a9%e3%83%a0%e6%b0%8f%](https://wired.jp/2007/10/26/%e3%80%8c%e3%82%a6%e3%83%ab%e3%83%95%e3%83%a9%e3%83%a0%e6%b0%8f%) e3%81%ae%e3%83%81%e3%83%a5%e3%83%bc%e3%83%aa%e3%83%b3%e3%82%b0%e3%83%9e%e3%82%b7%e3%83%b3%e3%80%8d%e3%82%9220%e6%ad%b3%e3%81%ae%e5 %ad%a6/]
Proof: Universality of Wolfram's 2, 3 Turing Machine [PDF](https://www.wolframscience.com/prizes/tm23/TM23Proof.pdf)
This is a 2-state, 3-color Turing machine
![image](https://gyazo.com/7c1f031187ef8a83356d06379039bd8d/thumb/1000)
We call this system 0.

System 1
- Read right of the head at B and branch out.
- ![image](https://gyazo.com/72f22a82439758fc8d409dc9d019b477/thumb/1000)
- This is just an equivalent system that compresses the steps and makes them easier for humans to understand.

System 2
- A third state was introduced.
- ![image](https://gyazo.com/e3ba9a9fda5723bb1ac8e996c8c98150/thumb/1000)
:
| -0- | -0- | -1- | -1- | -2- | -20 | -21 | -22 |
| -- | -- | -- | -- | -- | -- | -- | -- | -- | -- | -- | -- | -- |
|  A |  B |  A |  B |  A |  B |  B |  B |
| -1-  | -2-  | -2- | -2-  | -1-  | -00  | -12  | -11 |
|  __B | A__ | A__ | __B | A__ | __A | __B | __B |
| -0- | -0- | -0- | -1- | -1- | -10 | -11 | -12 | -2- | -20 | -21 | -22 | -2- |
|  A |  B |  C |  A |  B |  C |  C |  C |  A |  B |  B |  B |  C |
| -1-  | -2- | -2-  | -2-  | -2-  | -0-  | -1-  | -1-  | -1- | -0-  | -1-  | -1-  | -2- |
| __B | A__ | A__ | A__ | __B | __A | __C | __C | A__ | __A | __C | __C | __B |
- Instead of entering C in system 2, enter B and go right, then rewrite 1 for 2 and 2 for 1, matching system 1
:
| -21 | -22 |
| -- | -- |
| B |  B |
| -12  | -11 |
| __B | __B |
| -21 | -22 |
|  B |  B |
| -1-  | -1-  |
| __C | __C |
- Behavior when in system 2 and in state C is the same as the behavior when in system 1 and in state B, with 1 and 2 interchanged.
:
| -0- | -20 | -21 | -22 | -1- |
| -- | -- | -- | -- | -- |
|  B |  B |  B |  B |  B |
| -2-  | -00  | -12  | -11 | -2-  |
| A__ | __A | __B | __B | __B |
| -0- | -10 | -11 | -12 | -2- |
|  C |  C |  C |  C |  C |
| -2-  | -0-  | -1-  | -1-  | -2- |
| A__ | __A | __C | __C | __B |
- So, if we pass the tape from system 1 directly to system 2, the difference in rewriting when entering state C just cancels out the difference in judgment in state C, and it works fine.
- The reverse is also true, but when the starting state is C, the current position of the tape must be rewritten

![image](https://gyazo.com/7f79ad3c39327d35b96c65b418867a02/thumb/1000)

Using this system3, any non-negative integer can be represented by a single block of 1s and 2s separated by 0s
- Not exactly binary.

Realize a two-color cyclic tag system using System 5.

[[two-colour cyclic tag system]]
[Cyclic Tag System -- from Wolfram MathWorld](https://mathworld.wolfram.com/CyclicTagSystem.html)
- A tag system is one that applies n rules in sequence and then returns to the first rule
- The cyclic tag system is one in which the rule is in the form of "Add a pattern at the end when the beginning is 1. Those that have the form "Remove regardless of the leading value".

If we can get back to the two-color cyclic tag system, we can get back to the [[2-Tag system]] and we can get back to the Turing machine.
- [[Conversion of 2-tag system and 2-color recirculation tag system]]
- [[Tag system and Turing machine conversion]]

2-tag system and Turing machine
[https://dspace.mit.edu/bitstream/handle/1721.1/6107/AIM-052.pdf?sequence=2](https://dspace.mit.edu/bitstream/handle/1721.1/6107/AIM-052.pdf?sequence=2)

---
This page is auto-translated from [/nishio/2状態3色チューリングマシン](https://scrapbox.io/nishio/2状態3色チューリングマシン) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.