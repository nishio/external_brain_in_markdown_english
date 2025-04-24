---
title: "Merge of intellitech-en"
---

2022-01-20
- Greetings: [[ScrapboxAutoTrans Development Diary 2022-01-20]].
- Merge [/intellitech-en](https://scrapbox.io/intellitech-en) into this project
- ![image](https://gyazo.com/b07e82d4ba1e17841a60b1cd53a670c6/thumb/1000)
- ![image](https://gyazo.com/92f28c5bf9c53d50ef15ad9d5c6575bc/thumb/1000)
    - Unexpected things collide...
    - In the meantime, I'll change the title of the Japanese one to think about what to do after importing.
    - prefix: `(collision)`

add_icon_on_all_pages.py

```
import json
IN_FILE = "intellitech-en.json"
OUT_FILE = "intellitech-en-out.json"
ICON = "[en.icon]"
data = json.load(open(IN_FILE))
for p in data["pages"]:
    p["lines"].append({"text": ICON})

json.dump(data, open(OUT_FILE, "w"))
```


It's done.

Resolving Collision Pages
- Most pages are predominantly in English
- I wasn't sure what to do with just the George Edward Pelham Box.
    - There is a link to the Japanese page.
    - Decided to keep both.


[[pIntEn]]

---
This page is auto-translated from [/nishio/intellitech-enのマージ](https://scrapbox.io/nishio/intellitech-enのマージ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.