---
title: "400 Bad Request by hitting Flask from JS"
---

I'm hitting "Content-Type": "application/json", but Flask is receiving request.data and giving me a 400 Bad Request.
Using request.json

full sample:
ts

```typescript
const data = { user: "test", talk: "test", text: text };
fetch("https://keicho.herokuapp.com/api/web/", {
  mode: "cors",
  method: "POST",
  body: JSON.stringify(data),
  headers: {
    "Content-Type": "application/json",
  },
}).then((response) => {
  console.log(response);
});
```

python

```
@app.route('/api/web/', methods=["POST"])
def web_api():
    user = request.json.get("user")
    talk = request.json.get("talk")
    text = request.json["text"]
    return keicho.connect_web(user, talk, text)
```


---
This page is auto-translated from [/nishio/JSからFlaskを叩いて400 Bad Request](https://scrapbox.io/nishio/JSからFlaskを叩いて400 Bad Request) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.