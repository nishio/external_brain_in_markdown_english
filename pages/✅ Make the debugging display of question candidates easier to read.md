---
title: "✅ Make the debugging display of question candidates easier to read"
---

✅Make multi-line items in the citation display just the text of the question.
Ignore those that are not candidates with a ✅ score of 0
py

```
def debug_score_for_single_arg_question(env, qid, k, score):
    if score == 0:
        return
    res = questions[qid](env, (k,))
    if res[0] == "\n":  # omit quote
        res = res.splitlines()[-1]
    logger.debug((res, k, score))
```

---
This page is auto-translated from [/nishio/✅質問候補のデバッグ表示を見やすくする](https://scrapbox.io/nishio/✅質問候補のデバッグ表示を見やすくする) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.