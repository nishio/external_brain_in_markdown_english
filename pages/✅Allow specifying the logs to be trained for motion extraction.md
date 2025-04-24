---
title: "✅Allow specifying the logs to be trained for motion extraction"
---

relevance
    - [[Motion Extraction]]
    - [[Motion Extraction Work Memo]]

Currently, "text files written out in advance with one line and one remark" are used as the learning target.
This was good for learning before operation, but after actual operation, "This is how I reacted to this input" triggers re-learning, so you will want to use inputs that are not in this file.

ugoki/user.py

```
def _talkid_to_logs(talkid):
    data = json.load(open(f"{_HERE}/../../logs/cache/{talkid}.json"))
    for user, text in data["log"]:
        if user == 1:
            yield text

def get_unknowns():
    #logs = open(_RAW_LOGS).readlines()
    logs = _talkid_to_logs("alUKPkDIxF4BN18b4Yoe")
    for text in logs:
        for case in text_to_cases(text):
            yield case
```


You might think it would be a good idea to "target all logs" (and I actually did it a long time ago), but it's not good because there are some strange logs that keep posting meaningless strings of text and abusing bots.
- [[Ability to ignore strange users]] may be needed first.

---
This page is auto-translated from [/nishio/✅動きの抽出の学習対象ログを指定可能にする](https://scrapbox.io/nishio/✅動きの抽出の学習対象ログを指定可能にする) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.