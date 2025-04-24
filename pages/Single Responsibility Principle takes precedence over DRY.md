---
title: "Single Responsibility Principle takes precedence over DRY"
---

relevance
    - [[Trade-off between DRY and loosely coupled]]

- [[DRY principle]]
> [mizchi](https://twitter.com/mizchi/status/1668455243124969473) I think the [[single responsibility principle]] is far more important than [[DRY]], so I avoid putting together code, even if it's a bit verbose, and I'm pretty nervous about people refactoring in the name of DRY. I'm pretty nervous about reviews.

> [mizchi](https://twitter.com/mizchi/status/1668456734309122049) If anything, I think the DRY concept itself is even bad. If it is used in the cause of destroying the principle of single responsibility and mixing different codes of responsibilities, I would even say that the DRY concept itself is harmful.

> [mizchi](https://twitter.com/mizchi/status/1668458176101105665) It's easy to teach DRY when teaching refactoring to beginners. If it looks similar, it's DRY. But when code with different responsibilities is synthesized and becomes an inseparable mass that only solves a specific use case, you are really stuck.

> [mizchi](https://twitter.com/mizchi/status/1668458991347994624) It is not absolutely forbidden to mix different codes, but I think such codes are allowed if they are terminal helpers. For example, if it is a helper function for testing, it is acceptable to mix them. Conversely, helpers should not be bloated, and anything less than a helper should not be mixed.

> [mizchi](https://twitter.com/mizchi/status/1668461133341261825) Specifically, what kind of code is anti-pattern? The code to write the intermediate data passed to the View State in the web framework from the side and write it back to the Model.

---
This page is auto-translated from [/nishio/DRYより単一責任原則が優先](https://scrapbox.io/nishio/DRYより単一責任原則が優先) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.