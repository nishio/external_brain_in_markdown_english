---
title: "Try the Scrapbox API"
---

- /api/pages/<project_name>
    - CREATED, etc. contains integers.
        - It's supposed to be unixtime in seconds.
        - [Date - JavaScript | MDN](https://developer.mozilla.org/ja/docs/Web/JavaScript/Reference/Global_Objects/Date)
        - Multiply by 1000 and `new Date(x * 1000)` to get the date and time.
    - You can get it even if you are not logged in.
        - Then what's the value of ACCESSED...
- `No 'Access-Control-Allow-Origin' header is present on the requested resource.`
    - Oh, it's only accepting access from scrapbox.io?

    - [[Experiment with changing the sort order in Scrapbox]]
- [[ScrapboxAPI]]

---
This page is auto-translated from [/nishio/ScrapboxのAPIを試す](https://scrapbox.io/nishio/ScrapboxのAPIを試す) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.