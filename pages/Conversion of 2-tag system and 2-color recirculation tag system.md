---
title: "Conversion of 2-tag system and 2-color recirculation tag system"
---

- Conversion between [[2-Tag system]] and [Two-color recirculation tag system
- The [[cyclic tag system]] ([[Circular tag system]]), in which the string consists of only 0s and 1s, can realize a 2-tag system.

- structure
    - 2-Map the N types of characters that appear in the tag system to integers from 0 to N-1.
    - Map integer i to "a string of length N and only the i-th 1".
    - When the first letter is i, it is ~" becomes "When the i-th letter is 1, it is ~".
    - N empty rules for the removal of the second letter and skip the reading.
- Implementation [GitHub](https://github.com/nishio/turing_complete/blob/main/main/twotag.py)
- doubt
    - [Twitter](https://twitter.com/nishio/status/1378427366108622853): I'm talking about a 2-tag system that uses 3 different characters, converting each character to 100,010,001 and making 6 rules for each character replacement and an empty rule for skipping the 2nd character reading. The original CTS stops when the length is less than 1, but this one has to stop when the length is less than 6.
    - I converted the 2-tag system to a circular tag system to solve the Kolatz problem and it no longer stops.
    - So, what I'm trying to say is that if you add a new stop condition that says "stop when it falls below 6", that's not a CTS, so you need to rewrite something else, right? I mean.
    - You can't take "stop when the stop character comes first" to the circular tag system as it is, either...

---
This page is auto-translated from [/nishio/2-タグシステムと2色循環タグシステムの変換](https://scrapbox.io/nishio/2-タグシステムと2色循環タグシステムの変換) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.