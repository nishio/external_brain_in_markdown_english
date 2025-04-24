---
title: "replace the foundation"
---

![image](https://gyazo.com/0c7e0b19c6c45d470c74103aa3854f8f/thumb/1000)
After creating a certain program, I wanted to change the foundation of that program (how to have data, data structure, etc.).
I had a lot of trouble deciding whether to do it with a new project or change it from the current code.
    - [[Should we rebuild or not?" is a false choice.]]
- I was not sure what to do with it.

This time, after much discussion, the term "[[interface]]" emerged and the project moved forward.
First identify the interface where the data will be stored and attach a branch to that interface
Temporarily, data will be in the form of double holdings.
Then identify the interface that uses that data and replace it

![image](https://gyazo.com/960712b1d353d1f1102cdd67bd900cdc/thumb/1000)
This way, unlike rebuilding from scratch, part B serves as a sort of test.
And since I was writing in TypeScript this time, the type checking helped a lot,
It's also a test to see if the behavior changes after the switch.

In the process of doing it, I discovered a lot of oversights in the implementation of 'a', so I'm glad I was able to scaffold 'b'.
If they had to rebuild from scratch, they wouldn't have realized the design error until they implemented the B equivalent.

---
This page is auto-translated from [/nishio/土台を取り替える](https://scrapbox.io/nishio/土台を取り替える) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.