---
title: "Snap!"
---

- > [abee2](https://twitter.com/abee2/status/1371293853358039040): user-defined blocks have arguments but no return value (that's why they are procedures, not functions). Built-in functions (rounded reporter blocks at both ends, pointed boolean blocks) have return values.
    - > If you set the variable to "only this sprite" (instance variable), you can prevent the scope from expanding unnecessarily to some extent. If you can't allow it, you can use Snap! [https://snap.berkeley.edu](https://snap.berkeley.edu)
    - > "Only this sprite" namespace is that sprite, so calling simultaneously within it will cause name collisions. To avoid this, i.e., to make it re-entrant, you can either manage it in a list or create a clone for each call to the defined block. Only this sprite" is unique for each clone.

- > [abee2](https://twitter.com/abee2/status/1348885973078183938): You can't define functions in Scratch (only procedures with no return value can be created with block definitions), so even if you write one recursion, you have to manage the stack yourself. You have to manage the stack yourself, even if you write a single recursion. Blocks are not first-class objects, and you cannot create lambda expressions.
    - > For this purpose, we recommend Snap! Snap! Build Your Own Blocks [https://snap.berkeley.edu](https://snap.berkeley.edu)

---
This page is auto-translated from [/nishio/Snap!](https://scrapbox.io/nishio/Snap!) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.