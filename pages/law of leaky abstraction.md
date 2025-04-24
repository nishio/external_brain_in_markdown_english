---
title: "law of leaky abstraction"
---

[The Law of Leaky Abstractions – Joel on Software](https://www.joelonsoftware.com/2002/11/11/the-law-of-leaky-abstractions/)(2002)
> All non-trivial abstractions, to some degree, are leaky.
> All non-trivial abstractions are leaky to some degree.
    - The nuance that even if one tries to [[conceal]] the [[complexity]] of the [[lower layer]] by [[abstraction]], it cannot be completely concealed and the complexity will always "[[leak out]]".
- Lots of concrete examples in the book.
- It's an article from 2002, but it fits in with the current "age of AI writing programs that are now a reality" in 2024.
- I can't think of a good Japanese translation. Draft: [[Law of Leaky Abstraction]] / [["Abstraction has leaks" law]].

> Code generation tools which pretend to abstract out something, like all abstractions, leak, and the only way to deal with the leaks competently is to learn about how the abstractions work and what they are abstracting. So the abstractions save us time working, but they don’t save us time learning.
> Code generation tools that pretend to abstract something leak just like any other abstraction. And the only way to properly handle leaks is to learn how abstractions work and what they abstract. In other words, abstractions save time working, but they do not save time learning.
- [[Abstraction reduces work time, but not learning time.]]

> And all this means that paradoxically, even as we have higher and higher level programming tools with better and better abstractions, becoming a proficient programmer is getting harder and harder.
>  And all of this means, paradoxically, that it is increasingly difficult to become a skilled programmer, despite increasingly > higher-level programming tools with better abstractions.
- This is because the lower layers are less visible, hidden by the abstraction layer
- Before abstraction, things that you would naturally see in the course of doing your daily work are no longer visible due to abstraction.
- But "mastery" can only come through an understanding of the abstraction itself.

> And while these great tools, like modern OO forms-based languages, let us get a lot of work done incredibly quickly, suddenly one day we need to figure out a problem where the abstraction leaked, and it takes 2 weeks.
> These excellent tools, such as modern object-oriented form-based languages, can do a lot of work incredibly quickly, but then one day you need to figure out a problem with a leaky abstraction, and that takes two weeks.
In the next few years AI will be doing a lot of work incredibly quickly, and then one day it will need to figure out the problem that the abstraction leaked, and that will take two weeks. Whether this clarification takes one week or four weeks depends on the degree of understanding of how the abstraction works and what is being abstracted".


- [[abstract layer]]
[[Abstraction Layer]]

---
This page is auto-translated from [/nishio/リーキーアブストラクションの法則](https://scrapbox.io/nishio/リーキーアブストラクションの法則) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.