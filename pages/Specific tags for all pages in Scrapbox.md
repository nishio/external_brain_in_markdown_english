---
title: "Specific tags for all pages in Scrapbox"
---

I wrote this because I wanted to create a project for English translation by adding a "translation yet" tag to all the pages of the Scrapboxed project of the Japanese version of Engineer's Intellectual Production Techniques. It's too simple to publish as a tool, so I'll put it here.

python

```
import json
data = json.load(open("/Users/nishio/Downloads/test-scrapbook-20181215.json"))
for page in data["pages"]:
    page["lines"].extend(["", "[translation not yet]"])

json.dump(data, open("out.json", "w"))
```


---
This page is auto-translated from [/nishio/Scrapboxの全ページに特定タグをつける](https://scrapbox.io/nishio/Scrapboxの全ページに特定タグをつける) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.