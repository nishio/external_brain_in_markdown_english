---
title: "No means of recovery if keywords are split"
---

from [[pKeicho]]
No means of recovery if keywords are split
- > I may draw a secondary work of Pirika-chan
- >  What kind of Rika-chan is this Rika-chan?
- >  (I see. It's misidentified as "pi+rika")
- >  "Pirika-chan"
- >  Where is this Rika-chan?
- Actually, it is possible to force keywords by writing `[Pirika-chan]` (grammar for testing), but even if you do it once, the current implementation does not extract the expression "Pirika-chan" as a keyword after that, so it is very subtle.
- Once something is recognized as a keyword, it could be checked to see if it is included in every user input.

---
This page is auto-translated from [/nishio/キーワードが分割されてしまった場合のリカバリ手段がない](https://scrapbox.io/nishio/キーワードが分割されてしまった場合のリカバリ手段がない) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.