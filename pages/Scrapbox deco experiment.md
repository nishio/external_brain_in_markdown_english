---
title: "Scrapbox deco experiment"
---

I learned that if you do `[# aaa]` in Scrapbox, the span will have a deco-# class.
However, neither `[## aaa]` nor deco-## is attached, nor is deco-## nested, and it is indistinguishable from `[# aaa]`.
With `[() aaa]`, `deco-(` and `deco-)` are attached to one span. With `[)( aaa]`, they are attached in reverse order.
In other words, I think that `[## aaa]` is a situation where deco-# is given twice to the same span, resulting in one span.

Since the number of sharps cannot be identified, I thought of using #1, #2, and #3 as alternatives, but `[#1 aaa]` would not recognize #1 as deco. I guess there is a set of characters that are recognized as "symbols", and the system judges deco only when the first word consists of only those characters in the set.

I think it would be better if the deco words were attached in the form of `deco-###` instead of being broken up into letters, or if the deco words were nested, but why is this the case?

---
This page is auto-translated from [/nishio/Scrapboxのdecoの実験](https://scrapbox.io/nishio/Scrapboxのdecoの実験) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.