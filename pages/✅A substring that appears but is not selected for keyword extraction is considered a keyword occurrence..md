---
title: "✅A substring that appears but is not selected for keyword extraction is considered a keyword occurrence."
---

For example, if "lecture" is extracted as a keyword and then the statement "make lecture materials" is made, if [[keyword extraction]] extracts the range of "lecture materials" as a keyword, this would result in "B" being extracted independently of "A," which is not appropriate. In this case, "lecture" should also be regarded as appearing again.

Added [[✅Recurrences of short keywords are not treated as keywords.]]

make_response.py

```
# Consider substrings that are not selected in the keyword extraction but appear as keyword occurrences.
for k in env.scored_keyphrases:
    if k not in keyphrase and k in s:
        keyphrase[k] = min(100, env.scored_keyphrases[k])
```


---
This page is auto-translated from [/nishio/✅出現してるがキーワード抽出で選ばれてない部分文字列をキーワード出現とみなす](https://scrapbox.io/nishio/✅出現してるがキーワード抽出で選ばれてない部分文字列をキーワード出現とみなす) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.