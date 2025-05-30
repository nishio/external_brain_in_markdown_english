---
title: "Import to Scrapbox in Python"
---

Let's learn Node and Puppeteer because I found out that Puppeteer allows bots to live in Scrapbox!
→I'm learning Node and Puppeteer, and while I'm learning Node and Puppeteer, I don't need Puppeteer anymore.
→If I don't need Puppeteer, I can do it in Python without using Node, which I'm not familiar with... I'll give it a try.
→I got it.

python

```
import requests
from dotenv import load_dotenv
import json
import os

load_dotenv()

API_ME = "https://scrapbox.io/api/users/me"
API_IMPORT = "https://scrapbox.io/api/page-data/import/{project}.json"


def write_pages(pages):
    sid = os.getenv("SID")
    project = os.getenv("PROJECT")

    cookie = "connect.sid=" + sid
    r = requests.get(API_ME, headers={"Cookie": cookie})
    r.raise_for_status()
    csrfToken = r.json()["csrfToken"]

    url = API_IMPORT.format(project=project)
    data = json.dumps({"pages": pages})
    r = requests.post(
        url,
        files={"import-file": data},
        headers={
            "Cookie": cookie,
            "Accept": "application/json, text/plain, */*",
            "X-CSRF-TOKEN": csrfToken,
        }
    )
    r.raise_for_status()


def _test():
    pages = [
        {
            "title": "Scbot Home",
            "lines": ["Scbot Home", "Hello world!"]
        }
    ]
    write_pages(pages)
```

[https://github.com/nishio/scbot/blob/0.1/t.py](https://github.com/nishio/scbot/blob/0.1/t.py)

---
This page is auto-translated from [/nishio/PythonでScrapboxにimport](https://scrapbox.io/nishio/PythonでScrapboxにimport) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.