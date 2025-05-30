---
title: "Tag system and Turing machine conversion"
---

- Configure [[2-symbol Turing machine]] in [2-Tag system
Cocke, J., and Minsky, M.: "Universality of Tag Systems with P=2", J. Assoc. Comput. Mach. 11, 15–20, 1964. [PDF](https://dspace.mit.edu/bitstream/handle/1721.1/6107/AIM-052.pdf?sequence=2)

Turing machine] addressed in this paper.
- Two-symbol Turing machine that can only write 0 or 1 on the tape.
- The order of processing is slightly different for easier handling. First write, then move, then read, then state transition.
    - ![image](https://gyazo.com/6aa532eb91ba83783114bc7b3927c99c/thumb/1000)

tape
- ![image](https://gyazo.com/255f33e35d70524c80ed24698fb6f048/thumb/1000)
- Consider an infinitely long tape to be a binary notation for a single integer.
    - The process of moving the head can be written like this
        - ![image](https://gyazo.com/ae438265c9b51b7f8a41158e762673e6/thumb/1000)

tag system
- A mechanism to add a string determined by the first character of the queue to the end of the queue and remove the first two characters of the queue
    - Represent the contents of a Turing machine tape as "a string of two letters repeated N times".
        - (That's going to be a string of exponential order of tape length...)

The specific transformations to be made are not easy to understand if the paper's description in natural language is redone here in natural language.
- Implemented [GitHub](https://github.com/nishio/turing_complete/blob/main/main/twotag_turing.py)
    - One state of the Turing machine is transformed into 16 tag rules
    - It appears to be working correctly for the R's mentioned in the paper.
- Tag system rules made from a Turing machine that just moves one step to the right, reads the tape, and branches off.
:

```
>>> convert({"Q0": (0, "R", "Q1", "Q2")})
{'A_Q0': ['C_Q0', 'x_Q0'],
 'a_Q0': ['c_Q0', 'x_Q0', 'c_Q0', 'x_Q0'],
 'B_Q0': ['S_Q0'],
 'b_Q0': ['s_Q0'],
 'C_Q0': ['D1_Q0', 'D0_Q0'],
 'c_Q0': ['d1_Q0', 'd0_Q0'],
 'S_Q0': ['T1_Q0', 'T0_Q0'],
 's_Q0': ['t1_Q0', 't0_Q0'],
 'D1_Q0': ['A_Q2', 'x_Q2'],
 'd1_Q0': ['a_Q2', 'x_Q2'],
 'T1_Q0': ['B_Q2', 'x_Q2'],
 't1_Q0': ['b_Q2', 'x_Q2'],
 'D0_Q0': ['x_Q1', 'A_Q1', 'x_Q1'],
 'd0_Q0': ['a_Q1', 'x_Q1'],
 'T0_Q0': ['B_Q1', 'x_Q1'],
 't0_Q0': ['b_Q1']}
```

- Running it on a tape with only 0 shows that it does indeed transition to Q1
:

```
>>> run_tag_system({"Q0": (0, "R", "Q1", "Q2")}, "Q0", [], [])
['A_Q0', 'x_Q0', 'B_Q0', 'x_Q0']
['B_Q0', 'x_Q0', 'C_Q0', 'x_Q0']
['C_Q0', 'x_Q0', 'S_Q0']
['S_Q0', 'D1_Q0', 'D0_Q0']
['D0_Q0', 'T1_Q0', 'T0_Q0']
['T0_Q0', 'x_Q1', 'A_Q1', 'x_Q1']
['A_Q1', 'x_Q1', 'B_Q1', 'x_Q1']
['A_Q1', 'x_Q1', 'B_Q1', 'x_Q1']
```

- Write 1 on the right tape to transition to Q2.
:

```
>>> run_tag_system({"Q0": (0, "R", "Q1", "Q2")}, "Q0", [], [1])
['A_Q0', 'x_Q0', 'B_Q0', 'x_Q0', 'b_Q0', 'x_Q0']
['B_Q0', 'x_Q0', 'b_Q0', 'x_Q0', 'C_Q0', 'x_Q0']
['b_Q0', 'x_Q0', 'C_Q0', 'x_Q0', 'S_Q0']
['C_Q0', 'x_Q0', 'S_Q0', 's_Q0']
['S_Q0', 's_Q0', 'D1_Q0', 'D0_Q0']
['D1_Q0', 'D0_Q0', 'T1_Q0', 'T0_Q0']
['T1_Q0', 'T0_Q0', 'A_Q2', 'x_Q2']
['A_Q2', 'x_Q2', 'B_Q2', 'x_Q2']
['A_Q2', 'x_Q2', 'B_Q2', 'x_Q2']
```

- The number of repetitions of ax and bx expresses the state of the tape.
    - Whether it is 1 when moved and read is consistent with whether this number of iterations is odd or not.
    - When moving to the right, `B x b x b x ... `
        - The `B -> S, b -> s` conversion rule halves the length here.
        - S D1 D0` when tape is 0, `S s D1 D0` when tape is 1
        - Cutting off the first two tokens, the first two tokens are D0 and D1.
    - When moving to the left?
        - ![image](https://gyazo.com/fd60f1d5c87f52c04f2d014ae77765df/thumb/1000)
            - Change what needs to be changed."
            - Please write down where I should change...
        - Should we simply halve the tokens that are jammed with A and a?
            - There is a possibility that the tokens reproduced in B could be read half out of alignment.
                - Rule generation when going right
:

```
if move == "R":
    if write:
        add_rule("A", "C x c x")
    else:
        add_rule("A", "C x")
    add_rule("a", "c x c x")
    add_rule("B", "S")
    add_rule("b", "s")
    ...
```

                - If you invert this to the left...
:

```
  elif move == "L":  # incorrect impl.
      add_rule("A", "C")
      add_rule("a", "c")
      if write:
          add_rule("B", "S x s x")
      else:
          add_rule("B", "S x")
      add_rule("b", "s x")
```

                - I read x that shouldn't be read.
:

```
run_tag_system({"Q0": (1, "L", "Q1", "Q2")}, "Q0", [], [])
['A_Q0', 'x_Q0', 'B_Q0', 'x_Q0']
['B_Q0', 'x_Q0', 'C_Q0']
['C_Q0', 'S_Q0', 'x_Q0', 's_Q0', 'x_Q0']
['x_Q0', 's_Q0', 'x_Q0', 'D1_Q0', 'D0_Q0']
['x_Q0', 's_Q0', 'x_Q0', 'D1_Q0', 'D0_Q0']
Out[10]: ['x_Q0', 's_Q0', 'x_Q0', 'D1_Q0', 'D0_Q0']
```

        - Oh, so I just need to process A behind B first?
            - It would be two more states, but that would do it, and the test passed.


---
This page is auto-translated from [/nishio/タグシステムとチューリングマシンの変換](https://scrapbox.io/nishio/タグシステムとチューリングマシンの変換) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.