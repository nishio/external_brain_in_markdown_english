---
title: "ABC175F"
---

[F - Making Palindrome](https://atcoder.jp/contests/abc175/tasks/abc175_f)
- ![image](https://gyazo.com/de4ce184d63017d1bb7b3f0b430e77cc/thumb/1000)
    - [[palindrome]]
- Thoughts.
    - Select the first string
    - Limited number of strings that can come at the end.
    - Search in order of decreasing total cost and end when found.
    - After seeing the first and the last?
        - Depends on which is shorter.
        - Add on the short side
        - What if the length is the same?
            - That's a palindrome formation.
        - Palindromes may be formed even if they are different lengths.
            - Example a, ba
            - Need a low-cost determination of "is the palindrome established?"
                - The part left over when the longer one is cut at the length of the shorter one is the palindrome.
    - Sign of a trap
        - When you have a palindrome with a cost of 10^9 and a cost of 1 "parts that will not become a palindrome no matter how many combinations, but will continue to have palindromic possibilities", I feel like I would try the latter 10^9 times.
        - Is there such a pattern?
        - How about abc, a, cbcb, bcbc or something?
            - not serving its purpose
        - I can't think of anything, so I'm going to assume it's not there, implement it, and then reflect on it when the TLE gets mad at me.
- Official Explanation
    - Only retain the parts that are not palindromes."
        - I see, so once you get to the already existing pattern, it's a thousand days away, so you don't have to explore beyond that.
    - Graph possible transitions, with "blank" or "remainder is palindrome" as the goal [[shortest path problem]].
        - [[Shortest path problem for state transition diagrams]]

- [[unAC]]

---
This page is auto-translated from [/nishio/ABC175F](https://scrapbox.io/nishio/ABC175F) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.