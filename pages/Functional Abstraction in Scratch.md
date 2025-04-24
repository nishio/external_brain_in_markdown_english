---
title: "Functional Abstraction in Scratch"
---

The explanation by [abee2](https://twitter.com/abee2/status/1275263397341196291) was easy to understand, so I reprinted it.
- I read this and created [Sending messages to individual sprites in Scratch
    - > Objects cannot be assigned to variables (not first-class objects)
    - While this is true, it is possible to assign a unique ID to an object.
    - The ID can be put into a variable.
    - When sending a message, the ID can be put in the destination variable to enable processing equivalent to "sending a message to an individual object.

[abee2](https://twitter.com/abee2/status/1275263397341196291)
- >  [[Scratch]] is a text language (for example, if you change the language setting to Arabic, it becomes unreadable). Assembling blocks is the same as skipping parsing and building a syntax tree. The paradigm is a [[concurrent distribution]] [[event-driven]] instance-based [[object-oriented]] type language, so it is closer to the same family than logical or functional types.
- >  Abstraction in Scratch is about grouping objects (sprites) together, but it is a bit special because there is no inheritance or transfer. What you see is functional abstraction, the best example of which is "if you get to the edge, it bounces back". In other words, the high-performance library is built in from the beginning, so you can write abstractions for the problem domain.
- >  There are two ways to abstract functions by yourself: block definitions and messages, the former is the same as writing a procedure (not a function). The latter can be achieved using broadcast, which is the same as the GoF observer pattern (1:n sender/receiver relationship). This makes the code Scratch-like when written utilizing polymorphism.
- >  What makes Scratch different from other object-oriented languages is the extremely sparse coupling between objects. Objects cannot be assigned to variables (they are not first-class objects), and relationships between objects cannot be described statically. This is Scratch's biggest challenge. This idea comes from [[StarLogo]].

---
This page is auto-translated from [/nishio/Scratchにおける機能の抽象化](https://scrapbox.io/nishio/Scratchにおける機能の抽象化) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.