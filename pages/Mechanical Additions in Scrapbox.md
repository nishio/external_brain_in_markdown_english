---
title: "Mechanical Additions in Scrapbox"
---

background
- In [/dominion](https://scrapbox.io/dominion), sometimes I write about a card by looking at the English text and sometimes by looking at the Japanese text, and I want both links to be connected.
- After making a few by hand, I settled on "put the Japanese card name in the title" and "put a link to the English name in the body text".
- If this is not done for the remaining hundreds, the benefit of "connecting in both Japanese and English" will not be achieved.
    - I don't want to do it manually, so I'll generate it mechanically.
- I don't want to overwrite something hand-crafted with something machine-generated.
    - It has not been determined whether or not to add to what is already there, so I will add it anyway.

mounting
- First, export the current project with updated date and time
- See the Eiwa list.
    - If you already have a page, add it.
    - If not, create and add an older date.

python

```
import json
import from_enwiki
data = json.load(open('dominion.json'))

titles = [p["title"] for p in data["pages"]]
OLD = 946652400.0  # 2000-01-01
for line in open("jaen.txt"):
    ja, en = line.strip().split("\t")

    # generate contents
    lines = from_enwiki.parse(en)
    lines += ["", f""[Dominion Wiki https://wikiwiki.jp/dominiondeck/{en}]"]

    if ja in titles:
        print("exists", ja, en)
        for page in data["pages"]:
            if page["title"] == ja:
                page["lines"] += lines

    else:
        page = dict(
            title=ja,
            lines=[ja] + lines,
            updated=OLD)
        data["pages"].append(page)

json.dump(data, open("dominion_new.json", "w"), indent=2)
```




---
This page is auto-translated from [/nishio/Scrapboxで機械的加筆をする](https://scrapbox.io/nishio/Scrapboxで機械的加筆をする) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.