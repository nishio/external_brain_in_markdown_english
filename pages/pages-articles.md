---
title: "pages-articles"
---

[[Wikipedia]] dump pages-articles

python

```
def getPages():
    inPage = False
    ret = []
    for line in open(filename):
        if line.strip() == "<page>":
            ret.append(line)
            inPage = True
        elif line.strip() == "</page>":
            ret.append(line)
            yield ret
            ret = []
            inPage = False
        if inPage:
            ret.append(line)
```



---
This page is auto-translated from [/nishio/pages-articles](https://scrapbox.io/nishio/pages-articles) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.