---
title: "Tuple Spaces"
---

<img src='https://scrapbox.io/api/pages/nishio-en/o3-mini-high/icon' alt='o3-mini-high.icon' height="19.5"/>
Tuple spaces are a shared memory model for [[interprocess communication]] in a [[distributed system]]. The basic idea is based on the [[Linda]] model, which has the following features

- tuple.
- Information is shared by writing an ordered set of data ([[tuple]]) to a shared area (tuple space).

- Basic Operation.
- 1.write: add a tuple to the tuple space.
2. read: use pattern matching to reference (without deleting) tuples.
3. take: search for tuples by pattern matching and remove them from the tuple space as soon as they are taken.

- Loosely Coupled Communication
- Because processes do not communicate directly with each other, but asynchronously exchange data via tuple space, loosely coupled coordination is achieved in time and space.

This provides a simple and flexible mechanism for synchronization and coordination in distributed systems and parallel computing.

---

[https://github.com/apayne/pylinda](https://github.com/apayne/pylinda)
Very simple

---
This page is auto-translated from [/nishio/Tuple Spaces](https://scrapbox.io/nishio/Tuple Spaces) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.