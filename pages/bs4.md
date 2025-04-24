---
title: "bs4"
---

[Beautiful Soup Documentation — Beautiful Soup 4.4.0 documentation](https://www.crummy.com/software/BeautifulSoup/bs4/doc/)
python

```
data = open("quotes/1.html")
soup = bs4.BeautifulSoup(data, "lxml")

xs = soup("blockquote")
for x in xs:
    quote = x.text.strip()
    ref = x.nextSibling.nextSibling("a")[0]
    booktitle = ref.text.strip()
    s = ref.nextSibling
    page = re.search(r"(\d+)page", s).groups()[0].
    print(quote, booktitle, page)
```



---
This page is auto-translated from [/nishio/bs4](https://scrapbox.io/nishio/bs4) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.