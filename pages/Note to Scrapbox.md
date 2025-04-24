---
title: "Note to Scrapbox"
---

memo

js

```javascript
Array.from(document.querySelectorAll(".o-textNote__link")).map(x=>x.href).join(" ")
```


Cannot use `wget -i`.

I can do it with requests.
python

```
def crawl():
    urls = open("urls.txt").read().strip("'").split()
    for url in urls:
        print(url)
        fn = url.replace(PREFIX, "")
        r = requests.get(url)
        print(r)
        open(f"data/{fn}.html", "w").write(r.text)
```


Embedding other pages by "figure", it's a hassle because it's an iframe.
- If you can use the identifier part of the URL to connect with 2-hops, that's good enough for me.

---
This page is auto-translated from [/nishio/Note to Scrapbox](https://scrapbox.io/nishio/Note to Scrapbox) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.