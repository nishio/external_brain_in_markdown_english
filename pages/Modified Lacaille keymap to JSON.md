---
title: "Modified Lacaille keymap to JSON"
---

The keymap, which was fixed at 3 bytes due to lack of ObjectiveC power in the previous modification, is now variable length by reading from JSON. (However, the maximum length is 256 bytes due to lack of ObjectiveC power.
- [[NSJSONSerialization]]
- [https://github.com/nishio/Lacaille/commit/168bd9e2cadbbdd48449cfb2f05d83bfe258266e](https://github.com/nishio/Lacaille/commit/168bd9e2cadbbdd48449cfb2f05d83bfe258266e)

---
This page is auto-translated from [/nishio/改造LacailleのキーマップをJSONにした](https://scrapbox.io/nishio/改造LacailleのキーマップをJSONにした) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.