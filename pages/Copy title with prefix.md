---
title: "Copy title with prefix"
---

- I was going to include existing private project pages in doing [[public to private transfer]], but decided to keymark those pages ([[to🔒]]).
So I decided to import the key mark and the project name as well as the page title.
python

```
def copy_with_prefix(src, dst):
    r = export_from(src)
    pages = r.json()["pages"]
    for p in pages:
        p["title"] = f"🔒{src}/" + p["title"]

    write_pages(dst, pages)
```


---
This page is auto-translated from [/nishio/タイトルにプレフィックスをつけてコピー](https://scrapbox.io/nishio/タイトルにプレフィックスをつけてコピー) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.