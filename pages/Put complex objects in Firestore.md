---
title: "Put complex objects in Firestore"
---

- Environment object of [[Listening Chat System]] was put in [[Firestore]].

- 1: Trying to put obj.__dict__ as is
    - →`"Cannot convert to a Firestore Value"`
    - Some fields are of a type that cannot be put into Firestore
- 2: Convert to json
    - [[defaultdict]] changed to dict, KeyError in later use
    - TUPLE changes to LIST.
        - This is used for dict keys, so it can't be aligned to a list.
        - Writing conversion functions

Serialization of complex objects is full of pitfalls
I wrote that after I got stuck, but I should have written a "test to see if what you put in will be restored" from the beginning.

---
This page is auto-translated from [/nishio/Firestoreに複雑なオブジェクトを入れる](https://scrapbox.io/nishio/Firestoreに複雑なオブジェクトを入れる) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.