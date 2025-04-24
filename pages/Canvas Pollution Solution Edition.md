---
title: "Canvas Pollution Solution Edition"
---

- [[canvas pollution]] solution

I wrote [[proxy server]] in [[Flask]].
python

```
import requests
from flask import Flask
from flask import Response

app = Flask(__name__)


@app.route('/gyazo.com/<hash>')
def gyazo(hash):
    url = f"https://gyazo.com/{hash}/thumb/400"
    r = requests.get(url, allow_redirects=True)
    r = Response(r.content, mimetype="image/png")
    r.headers['Access-Control-Allow-Origin'] = '*'
    r.headers['Cache-Control'] = 'max-age = 31536000'
    return r
```



---
This page is auto-translated from [/nishio/キャンバス汚染解決編](https://scrapbox.io/nishio/キャンバス汚染解決編) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.