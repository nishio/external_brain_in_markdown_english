---
title: "✅Bug that causes a blank page"
---

cause
- LastUpdated is 0 by default
- When a map is loaded from the server, if the lastUpdate of the data is older than the lastUpdate on hand, the screen is not updated.
- Forgot to update lastUpdated on load.
- As a result, when I do "load the map and save as" without editing, I get data with lastUpdated of 0.
- When this is loaded, there is no screen refresh because there are 0 on hand and 0 loaded.
revision (e.g. of a rule, regulation, etc.)
- Update lastUpdated on load
- Since broken data with lastUpdated of 0 has already been created, overwrite it with the current time if 0 as a workaround.

---
This page is auto-translated from [/nishio/✅白紙になるバグ](https://scrapbox.io/nishio/✅白紙になるバグ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.