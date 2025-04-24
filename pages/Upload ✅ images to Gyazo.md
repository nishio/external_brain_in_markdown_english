---
title: "Upload ✅ images to Gyazo"
---

python

```
def upload_to_gyazo(asin):
    local_filename = f"gyazo_cache/{asin}.txt"
    if os.path.isfile(local_filename):
        return open(local_filename).read()

    url = 'https://upload.gyazo.com/upload.cgi'
    image_filaname = f"image_cache/{asin}.jpg"
    files = {'imagedata': (image_filaname, open(image_filaname, "rb").read())}
    r = requests.post(url, files=files)
    open(local_filename, "w").write(r.text)
    return r.text
```


PS
- You should fix the error message being written to the cache when there is an error uploading to Gyazo.
Upload image to [Gyazo
[[Gyazo API]]

---
This page is auto-translated from [/nishio/✅画像をGyazoにアップロード](https://scrapbox.io/nishio/✅画像をGyazoにアップロード) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.