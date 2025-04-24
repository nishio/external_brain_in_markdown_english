---
title: "Export Facebook Messenger to JSON"
---

Now that official functionality is available for JSON export, it's easier to format the conversation to meet your needs.
- Settings>Your Facebook Info>Download Personal Data>"Format: JSON" and "Create File"

python

```
from datetime import datetime
import json
data = json.load(open("inbox/XXXXXXXX/message_1.json"))

prev_date = ""
for m in reversed(data["messages"]):
    date = datetime.fromtimestamp(m['timestamp_ms'] // 1000)
    str_date = date.strftime("%Y-%m-%d")
    if str_date != prev_date:
        print(str_date)
        prev_date = str_date
    if "content" in m:
        sender = "T:"
        if m["sender_name"].startswith("Nishio"):
            sender = "N:"
        print(sender,
              m["content"].encode("latin-1").decode("utf-8"))
```


I used it for this.
- [[Calibration Session]]

About 5 lines Copilot wrote.
[https://twitter.com/nishio/status/1453992902279892993?s=21](https://twitter.com/nishio/status/1453992902279892993?s=21)

---
This page is auto-translated from [/nishio/Facebook MessengerをJSONエクスポート](https://scrapbox.io/nishio/Facebook MessengerをJSONエクスポート) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.