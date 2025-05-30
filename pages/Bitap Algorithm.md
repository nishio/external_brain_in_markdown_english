---
title: "Bitap Algorithm"
---

> Bitap algorithm is a string search algorithm that uses the parallelism of bitwise operations
>  Also called Baeza-Yates-Gonnet algorithm, Shift-and algorithm and Shift-or algorithm
>  [[ambiguous retrieval]], which is a feature not found in other string search algorithms.
- [Bitap algorithm - Wikipedia](https://ja.wikipedia.org/wiki/Bitap%E3%82%A2%E3%83%AB%E3%82%B4%E3%83%AA%E3%82%BA%E3%83%A0)
- > 'bitap' (bit-parallel approximate pattern matching)

- Implemented in [[asearch]].

Start with a simple "unambiguous search" explanation
![image](https://gyazo.com/32dc88bb9200d0663c6cdc643ea29938/thumb/1000)
Use this kind of linear [[NFA]] to determine string acceptance.
Pack 1 bit of whether or not you are in each state into an integer so you can use AND and shift operations.
In the case of this figure
- Initial condition 100
- Acceptance state mask accept 001
- Mask corresponding to character a 100
- Mask corresponding to character b 010
    - The bit stands in the root state where the arrow grows that transitions to the next state in that character.
- State update: `state = (state & mask) >> 1`.
- Acceptance decision: `state & accept ! = 0`

This pattern matches "ab" in regular expression. *a.*b", but you can easily change it to match ".
![image](https://gyazo.com/0af6aed29ac322dd24d4577d7490b892/thumb/1000)

- Masking transitions with arbitrary characters eps 110
    - Bits stand in the root state of the growing transition in any character.
- state update: `state = (state & eps) | (state & mask) >> 1`.
    - Once the standing state of 1 in the eps mask is 1, it will remain 1 for the rest of the time.
- The implementation of [[asearch]] uses 0x20 as the character meaning this transition

ambiguous retrieval
![image](https://gyazo.com/4fc58b867e8bbde5eaafafd6cf7d75da/thumb/1000)
- Express a pattern that tolerates a single character error as a separate integer
    - I was going to explain each of these transitions (1), (2), and (3), but there seems to be a discrepancy between the diagram in the explanation and the implementation.
- Regarding the transition in (3)
    - The figure in [/masui/ambiguous search asearch](https://scrapbox.io/masui/ambiguous search asearch) is b
    - ![image](https://gyazo.com/d3884cc7d269be9eed5de95a28b261f0/thumb/1000)
    - However, asearch's implementation does `i1 |= (i0 >> 1)` after updating i0, so the transition is at a.
    - The implementation of "*" transitions and asearch in this figure appear to be "transitions with any one character" rather than "epsilon transitions that do not consume a character".
        - (Although the variable name epsilon is used in the asearch implementation.)
    - hence
        - If implemented as shown in the NFA diagram, "ab" accepts "b" and does not accept "a
        - The current implementation of asearch accepts "a" and does not accept "b
    - If the transition is an epsilon transition that does not consume a character, both "a" and "b" are accepted even without the Katsurabayashi transition (3).
        - ![image](https://gyazo.com/515ce7163d379ad3ffc1c5368a9c456b/thumb/1000)
        - Not yet examined whether it would be easy to implement this in bitwise operations.

[https://github.com/masui/asearch-ruby](https://github.com/masui/asearch-ruby)
ruby

```
chars.each { |c|
  mask = @shiftpat[c]
  i3 = (i3 & @epsilon) | ((i3 & mask) >> 1) | (i2 >> 1) | i2
  i2 = (i2 & @epsilon) | ((i2 & mask) >> 1) | (i1 >> 1) | i1
  i1 = (i1 & @epsilon) | ((i1 & mask) >> 1) | (i0 >> 1) | i0
  i0 = (i0 & @epsilon) | ((i0 & mask) >> 1)
  i1 |= (i0 >> 1)
  i2 |= (i1 >> 1)
  i3 |= (i2 >> 1)
}
```


- Look at the definition of [[Levenshtein Distance]] and think about what transitions there should be.
- ![image](https://gyazo.com/222b0f954e5cbd652709f8af937e4958/thumb/1000)
    - Inserting a single character is only required if a transition to the top occurs when any single character arrives, regardless of the character, so
        - `i1 |= i0`
    - The one-character replacement is good if the transition to the upper right occurs when any one character arrives, regardless of the character, so
        - `i1 |= (i0 >> 1)`
    - It is troublesome that one character deletion is an epsilon transition that does not consume a character.
        - Transition to "when the previous character arrives" while you are at it.
        - So after the character-consuming transition `i1 |= (i0 >> 1)`
    - Think of it this way, there is no problem with the transition part of asearch's implementation
    - Here's the problem.
ruby

```
def initstate
  [INITPAT, 0, 0, 0]
end
```

        - The epsilon transition before the first character comes in, i1 to i3 should also have bits standing, but they are set to 0.
    - As for the diagram, if you draw it using the epsilon transition, it means that the diagonal transition includes epsilon, but if you draw it without using it, that diagonal transition is a two way transition by the mechanism of [[Bitap algorithm#5ca57e73aff09e0000f994fd]], so both a and b for the cinnabar jumping line Therefore, it seems correct to draw both a and b on the cinnabar jumping line.


Other Topics
- The mask (shiftpat) for each character indicates "which state is the transition source when the character arrives", so for example, if you set up bits in both the mask for "a" and the mask for "A", case-insensitive matching is possible.
    - Not just case-insensitive, but any type of transition with multiple types of single characters. For example \d.
- On the other hand, "character-by-character mask" is required for each character, so it is necessary to devise a way to match a Japanese string.
    - The asearch implementation splits a character into multiple bytes and matches byte by byte.
        - cons: A difference of one character in Japanese is the same as a difference of two characters in fuzzy search
            - If one of the two bytes happens to match, it's a one-letter difference.
    - In my implementation, I only take the lower 1 byte of information and discard the rest.
:

```
>>> ensure_bytes("Hello")
b'S\x93kao'
```

        - We consider the probability that the lower 1 byte of a Japanese string of some length (from 5 characters) happens to be a string that makes sense in an ASCII string to be negligibly small.
            - cons: If you use 0x20 for a special meaning character like in the asearch implementation, you will get unexpected behavior when a Japanese character happens to be that character.

- velocity
    - I did an ambiguous search with a query of length 20 on a set of 25743 page titles obtained by crawling Scrapbox and found min 29, max 47, med 33 msec.

---
This page is auto-translated from [/nishio/Bitapアルゴリズム](https://scrapbox.io/nishio/Bitapアルゴリズム) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.