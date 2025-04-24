---
title: "Transfer HTTPS to HTTP on Heroku"
---

I wanted to receive a webhook and do a little processing.
- I don't want to set up an HTTPS server on server X that handles that process because it's a pain in the ass to manage certificates.
- Received by Heroku and forwarded to server X via HTTP.
- (After I did it, I thought that Lambda might have been better)

python

```
from flask import Flask, request
import requests
app = Flask(__name__)


def create_app():
    return app


@app.route('/', methods=['GET', 'POST'])
def root():
    if request.is_json:
        print(request.json)
        requests.post("http://...../", json=request.json)
    return "OK" 
```


relevance
- [[Heroku+Flask]]

---
This page is auto-translated from [/nishio/HerokuでHTTPSをHTTPに転送](https://scrapbox.io/nishio/HerokuでHTTPSをHTTPに転送) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.