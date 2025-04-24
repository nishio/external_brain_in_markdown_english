---
title: "Miro API"
---

[REST API reference guide](https://developers.miro.com/docs/rest-api-reference-guide?utm_source=chatgpt.com)

Sticky notes can be added.

![image](https://gyazo.com/245c91fa25cfaffb74de060cd078b6b8/thumb/1000)
python

```
import requests

ACCESS_TOKEN = ...
BOARD_ID = ...

def create_sticky(content, x, y):
    url = f"https://api.miro.com/v2/boards/{BOARD_ID}/sticky_notes"
    headers = {
        "Authorization": f"Bearer {ACCESS_TOKEN}",
        "Content-Type": "application/json",
    }
    data = {"data": {"content": content}, "position": {"x": x, "y": y}}
    resp = requests.post(url, json=data, headers=headers)
    resp.raise_for_status()
    return resp.json()["id"] # ID of created sticky


def create_connector(start_id, end_id):
    url = f"https://api.miro.com/v2/boards/{BOARD_ID}/connectors"
    headers = {
        "Authorization": f"Bearer {ACCESS_TOKEN}",
        "Content-Type": "application/json",
    }
    data = {
        "startItem": {"id": start_id},
        "endItem": {"id": end_id},
        "style": {"strokeColor": "#FF0000"},
    }
    resp = requests.post(url, json=data, headers=headers)
    resp.raise_for_status()
    return resp.json()


if __name__ == "__main__":
    # Create two stickies
    sticky_a_id = create_sticky("sticky A", 100, 100)
    sticky_b_id = create_sticky("sticky B", 400, 100)

    # Connect stickies to each other with connectors
    connector = create_connector(sticky_a_id, sticky_b_id)
    print("Connector created:", connector)
```

Easy!
Hard to know where to get ACCESS_TOKEN
- Obtaining an access token
    - Create your app in Miro's developer portal and
        - "Install app to get OAuth token"

[[Miro]]
- [[tag]]  / [[Sticker]]

---
This page is auto-translated from [/nishio/Miro API](https://scrapbox.io/nishio/Miro API) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.