---
title: "Kozane-clone-tear-merge"
---

2023-02-12
![image](https://gyazo.com/2ba9026b20de2affb680588ef2b4aab5/thumb/1000)

I thought Kozaneba had a line-drawing feature and I started drawing more and more lines, but I didn't think I needed this feature.

How is this going to happen?
- Rather, like this?
    - First, tear it into six pieces.
    - Combine a selection of kozane into one
        - If they are the same string, group them together; otherwise, join them with a space or slash between them.
    - Double lines are drawn later.


[[2023-02-27]] Implementation

update_annotation_after_deletion
- Implementation of "leave from line
- use as reference

- temporary suspension (of an application)
    - Display menu only when two or more lines are connected.
    - Move the lines in the direction they are connected.

![image](https://gyazo.com/e4cb4ce2eedafb1dd7e276e740a14fb8/thumb/1000)

It's done.
- But, as expected, "it's hard to tell which one is connected to which one when they're completely overlapping" is occurring.
    - I moved the second X thinking it was connected to A and it was actually connected to C.

[["Move in the direction of the line connection"]] Done.
- ![image](https://gyazo.com/07aa6880edfe0b1936bd0a299969057c/thumb/1000)


Next, merge
- Same content text in one
- Different content text is separated by slashes
- Scrapbox Kozane to the same page in one
- So what if they are mixed?
    - Stop doing that kind of...
- What if we merge the two ends of the line?

temporary suspension (of an application)
- Scrapbox Kozane Merge
- anomalous condition

I got as far as making a merged Kozane.
- Do what's on the left first.
What you need to do next
- line switching
- Delete Kozane before merging


Bug with misaligned coordinates when ungrouping inside a double group.

It's done.
    - ![image](https://gyazo.com/96efdbee11b617cbc8e99081a782c4d2/thumb/1000)

Tear Tear
- Tear off a kozane that has two or more lines connected to it.
Merge Annexation
- Combines a selection of kozanes into one.

- Remove Split Kozane functionality
    - It was an overly abstract feature created at a time when it was not yet clear what kind of functionality was needed.
    - The Edit Kozane and Clone functions are sufficient
    - Editing with the Edit Kozane function replaces Kozane
        - ![image](https://gyazo.com/dc88bce8e7d7026200144882cd031f52/thumb/1000)
    - If you make multiple lines at this time, you will have multiple sheets.
        - ![image](https://gyazo.com/c4c13c5426c9f11e3ffa3b09ff1e68b9/thumb/1000)
    - So, the need to "add something and later split it into multiple pieces" can be achieved with the Edit Kozane function.
    - The Split Kozane dialog had two buttons: "replace" and "add
        - This was the idea: "Sometimes you want to keep an existing one and add a split of it.
        - Now that the clone function has been added, I can clone when I think "I want to keep this", so I don't need it anymore.
        - ![image](https://gyazo.com/595f87314e6510fb529520abd2b0e69c/thumb/1000)

- Notes on specifications at this time
    - If you edit Kozane, if the text is a single line, it is interpreted as editing the display text.
        - So the lines drawn will be maintained.
    - If the text is multi-line, it is interpreted as a kozane division.
        - At this time, "old kozane" disappears and "import of multi-line text" is performed
        - So lines drawn on old stickies will disappear.
    - Since clone is interpreted as "adding a new kozane with the same contents", no line is drawn.
- I thought it might be tricky to write a commentary, so I specified it clearly.
    - Nishio hasn't had any trouble so far with these specs.
    - If you have a choice between a default specification with more lines and a default specification with no lines, you can say that you have chosen the one with no lines.
    - People get confused when there are too many lines, so I prefer not to have more!

use case
![image](https://gyazo.com/564bef46de6c46a37ef89684f6e93d18/thumb/1000)

---
This page is auto-translated from [/nishio/Kozane-clone-tear-merge](https://scrapbox.io/nishio/Kozane-clone-tear-merge) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.