---
title: "Multitasking and Copy GC"
---

[2014-01-03 Facebook](https://www.facebook.com/nishiohirokazu/posts/10202395816113270)
When I talked to my wife, our resident consultant, about the tight time available for writing, she said, "You are extremely bad at [[multitasking]], aren't you?

Wife: "If we can't multitask, then we have to think about how to improve performance with single-tasking. If we can't eliminate interrupts, then we have to reduce the cost of recovering from them."
I said, "I see, faster context switches."

So I looked into the difference in their behavior patterns, and found that the difference was that I write my TODOs in a notebook, while my wife writes them on a bundle of lined paper.
The difference is that my wife's [[copy GC]] runs at least once a day, whereas mine only runs about twice a month. Lowering the cost of paper makes it possible to use and discard it in a wealthy way.

Wife: "If you have so many minutes that it's painful to refresh once a day, that's too much writing."
Wife: "If your TODO list paper is full in the morning, you're writing too much because there's not enough space to write down the events that will happen that day."
There is a bias toward writing compacts.
Compact and can be loaded at a glance.
Lazy writing in a notebook won't make this happen.
---
This page is auto-translated from [/nishio/マルチタスクとコピーGC](https://scrapbox.io/nishio/マルチタスクとコピーGC) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.