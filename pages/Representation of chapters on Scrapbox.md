---
title: "Representation of chapters on Scrapbox"
---

What we think is best at the moment:.
- "(Section number)" at the beginning of the title
- Columns are prefixed with "(Column)", not in a chapter tree.
- [/intellitech-en](https://scrapbox.io/intellitech-en) in sort by title.
    - Pages in chapters are displayed in order, then columns, then other keywords.
    - Same order when converting to e-books

    - What we learned while working on [Project for English-language intellectual production techniques for engineers (-20200122)
- The original book did not have section numbers, but rather a way of referring to "~ on page X" or "in chapter X".
- In digitizing this, page numbers become meaningless.
- So I decided to number the sections.
- `1: Chapter 1`, `1.2: Chapter 1, Section 2`, `1.2.3: Chapter 1, Section 2, Section 3`.
    - The existence of `1.2:` and `1.2 ` distortions was weird.
        - for some reason
        - At first I thought just "X.X.X" would be fine, but then I got confused that if there is less than one period, it is a ground sentence, not a number.
        - In some cases, the number is at the beginning of the title. "47% of ~"
- I found out when I made it, this is a problem when searching by section number.
    - When I try to access 2.3 and search for 2.3.4 and 1.2.3, I get hits on 2.3.4 and 1.2.3 as well.
    - If I add a semicolon at the end of the number, I can make it not hit 2.3.4, but still hit 1.2.3.
    - It's especially bad because the higher the structure, the more titles that contain that number as part of it.
    - So there needs to be a symbol before and after
        - If this symbol is chosen appropriately, the sort order will be broken.
:

```
["1:", "1.1:", "1.1.1:"].sort()
["1.1.1:", "1.1:", "1:"]

["1)", "1.1)", "1.1.1)"].sort()
["1)", "1.1)", "1.1.1)"]
```

        - The colon is after the number in ASCII code.
- I've added branch numbers as "X-Y" or "X_Y", but Scrapbox equates underscores with spaces, so the latter is blank.

---
This page is auto-translated from [/nishio/Scrapbox上で章立てを表現](https://scrapbox.io/nishio/Scrapbox上で章立てを表現) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.