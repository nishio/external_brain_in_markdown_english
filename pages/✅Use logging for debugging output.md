---
title: "✅Use logging for debugging output"
---

I debugged the output with print, and it was too much work to display what I wanted, so I felt it was a shame to delete it, so I left it commented out, and now I need it again.
- You can use logging instead of print for that kind of thing.
    - before
action.py

```
score = score_for_single_arg_question(env, qid, k, maxScore)
# print(repr(questions[qid](env, (k,))), k, score)
```

    - after
action.py

```
import logging
logger = logging.getLogger(__name__)
...
logger.debug((res, k, score))
```

        - This is not the main topic here [✅ Make the debugging display of question candidates easier to read

If you set the log level to DEBUG only when a specific condition is met in the code on the side that calls the module, debug output will be generated only then.
- Since `__name__` in action.py is `"server.keicho.action"`, which represents the package hierarchy, you can use it to select a part of the entire source code and turn on/off debugging display.
python

```
import logging
logging.basicConfig()
...
if some_condition:
    logging.getLogger("server.keicho.action").setLevel(logging.DEBUG)
else:
    logging.getLogger("server.keicho.action").setLevel(logging.INFO)
```


---
This page is auto-translated from [/nishio/✅デバッグ出力にloggingを使う](https://scrapbox.io/nishio/✅デバッグ出力にloggingを使う) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.