---
title: "Test of preservation"
---

- When the item was moved, the local update flag was not set and it was not saved on the server.
- Compared to "the stacking order is wrong" or "it looks wrong", "I thought I was writing to the server, but I didn't" or "I wrote corrupt data" are much more serious, so they seem to have a higher priority than the apparent test.
- If I want to write a test case that says, "If I do this operation from this initial state, this kind of write should be done to the server," I need to be able to replace the write part to the server with a mock...
- If you try to do something like "save locally when offline," you'll need to disconnect anyway.

---
This page is auto-translated from [/nishio/保存のテスト](https://scrapbox.io/nishio/保存のテスト) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.