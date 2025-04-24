---
title: "sumitb2019_e"
---

[E - Colorful Hats 2](https://atcoder.jp/contests/sumitrust2019/tasks/sumitb2019_e)
- ![image](https://gyazo.com/6c88078c52ad01b746ded9146ff2b61d/thumb/1000)
- Thoughts.
    - DP maybe.
    - The first person's statement is zero information.
    - The first person's hat should be red, and later it can be multiplied by three.
    - The next person who answered 0 is blue.
    - Is there a pattern where the number of cases increases that much?
    - When you come to 0,0,0,1, there are three different colors for this person.
    - DP or DP with the number of people per color in the foreground as the defining area.
:

```
for (a, b, c) in memo:
	if a == x:
		push((a + 1, b, c))
	if b == x:
		push((a, b + 1, c))
	if c == x:
		push((a, b, c + 1))
```

    - So that's what it means.
    - I don't know how to update this efficiently, though.
    - Will there not be that much more variety?
    - Most of the time it's 1x, and the maximum is 3x, but after that it's confirmed that it won't be 3x, and it won't increase much.
- Official Explanation
    - Ah, I see, there is no need to distinguish between a, b, and c.
        - [[How can this realization be put into words?]]

---
This page is auto-translated from [/nishio/sumitb2019_e](https://scrapbox.io/nishio/sumitb2019_e) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.