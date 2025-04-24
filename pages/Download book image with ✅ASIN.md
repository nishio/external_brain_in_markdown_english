---
title: "Download book image with ✅ASIN"
---

python

```
def download_amazon_image(asin):
    url = f"http://images-jp.amazon.com/images/P/{asin}.09.LZZZZZZZ.jpg"
    local_filename = f"image_cache/{asin}.jpg"
    if os.path.isfile(local_filename):
        return
    with requests.get(url, stream=True) as r:
        r.raise_for_status()
        with open(local_filename, 'wb') as f:
            for chunk in r.iter_content(chunk_size=8192): 
                # If you have chunk encoded response uncomment if
                # and set chunk_size parameter to None.
                #if chunk: 
                f.write(chunk)
```


[Download large file in python with requests - Stack Overflow](https://stackoverflow.com/questions/16694907/download-large-file-in-python-with-requests)
[[requests]]

---
This page is auto-translated from [/nishio/✅ASINで書影画像をダウンロード](https://scrapbox.io/nishio/✅ASINで書影画像をダウンロード) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.