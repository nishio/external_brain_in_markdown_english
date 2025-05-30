---
title: "Return-related 2"
---

- [Developing the Power of Attribution

Last time [[landing practice]] I created several pages of issues at once, but I found that doing it in Scrapbox was a pain later!
- Discussion: [[Nodal Point of Thought 2020-12-18]].
Instead of making a lot of pages, I'd prefer to make a big page with everything in it and then divide it up.

Last time I used AtCoder Problems recommendations.
But the return training does not make it AC, so it remains at the top of the list and inconvenient.
After all I seem to be good at solving blue problems, so it would be better to solve blue problems such as ABC from the end

Maybe I'll do AGC in order of newest to oldest.

[https://atcoder.jp/contests/agc049/tasks/agc049_a](https://atcoder.jp/contests/agc049/tasks/agc049_a)
[[AGC049]]A

[[AGC048]]B

[[AGC047]]B
[https://atcoder.jp/contests/agc047/tasks/agc047_b](https://atcoder.jp/contests/agc047/tasks/agc047_b)
- Judging each string pair against each other will not make it in time.
- If you do some kind of processing on each string, you need a system that can find it on its own.
    - [[Special Constraint Issues]]
    - The total string length is held down by 10^6.
- What is a matched string pair?
    - When the length of the shorter one is n, the last n-1 characters match, and the remaining one character is contained in both.
- Sort in shortest order beforehand, flag the 26-character array for n-1 character matches, and increment the solution when that character appears
- How to do "n-1 character match"
- Do you want to put it in a try tree?
- I heard that policy is good, but there is also a rolling hash, apparently.

[https://atcoder.jp/contests/agc043/tasks/agc043_b](https://atcoder.jp/contests/agc043/tasks/agc043_b)
    - [[Once you're in a certain state, you can't get out.]]
- All values are 0 to 2" in one step.
- The only ones that end in 2 are all 0's and 2's on one end.
- 2 is not maintained unless there is a 0 next to it, which generally disappears rather quickly.
- But sometimes it doesn't go away, so I don't know what to do.

---
This page is auto-translated from [/nishio/帰着関連2](https://scrapbox.io/nishio/帰着関連2) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.