---
title: "The downside of thin libraries"
---

python

```
import slackweb
client = slackweb.Slack(url="...")
client.notify(text="Hello!")
```


python

```
import requests
requests.post(url, json=dict(text="Hello!"))
```


There's a problem that makes it hard to see these lower layers.
The lower layers change slowly and the upper layers change quickly, so one should delve into the lower layers to gain knowledge that is less prone to [[obsolescence]], but the thin library in between prevents this.

---
This page is auto-translated from [/nishio/薄いライブラリの弊害](https://scrapbox.io/nishio/薄いライブラリの弊害) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.