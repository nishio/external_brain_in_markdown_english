---
title: "Get OCR results from Gyazo Pro via API"
---

python

```
import requests

GYAZO_API_TOKEN = "..."
GYAZO_API_ROOT = "https://api.gyazo.com/api"
GYAZO_IMAGE_ID = "bf881c1e44d798978431f9a2af02acdb"

res = requests.get(
    f"{GYAZO_API_ROOT}/images/{GYAZO_IMAGE_ID}", headers={
        "Authorization": f"Bearer {GYAZO_API_TOKEN}"
    }
)
print(res.json()["ocr"]["description"])
```


PyPI has [[python-gyazo]], but it is not implemented to get a single image by specifying its ID, and "ocr" in the response is ignored, so you have to do a lot of work to use it for this purpose, and as mentioned above, you can achieve your goal in a few lines, so there was no need to use it.
[https://github.com/ymyzk/python-gyazo/blob/master/gyazo/api.py](https://github.com/ymyzk/python-gyazo/blob/master/gyazo/api.py)

[[OCR]]
[[Gyazo API]]

---
This page is auto-translated from [/nishio/Gyazo ProのOCR結果をAPIで取得](https://scrapbox.io/nishio/Gyazo ProのOCR結果をAPIで取得) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.