---
title: "POST JSON with requestss"
---

python

```
payload = {"q": sample_text}
r = requests.post(API_URL, json=payload)
```

The above code is fine.
- The following works as well. I use it a lot, so there's a shortcut provided.
- I thought I would need to encode the string since it contains Japanese characters, but that is done internally when converting it to JSON, so I don't need to do it myself.
    - Rather, if you do it, you get `TypeError: Object of type bytes is not JSON serializable` because bytes is not JSON compatible.

python

```
payload = json.dumps({"q": sample_text})
headers = {'content-type': 'application/json'}
r = requests.post(API_URL, data=payload, headers=headers)
```


---
This page is auto-translated from [/nishio/requestsでJSONをPOST](https://scrapbox.io/nishio/requestsでJSONをPOST) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.