---
title: "ppoi improvement 2021-02-05"
---

- [[Motion Extraction Work Memo]]
I assumed that the unjudged data was written in the file unknown.txt with one case per line in previous versions.
It was hard to use it, so I made it a generator.
python

```
def get_unknowns():
    logs = open(_RAW_LOGS).readlines()
    for text in logs:
        for case in text_to_cases(text):
            yield case
```


The user's customization is now in user.py, and the default implementation is in default.py.
python

```
from .user import (
    make_features, print_case, write, case_from_str, case_to_str, get_unknowns,
    MODEL_NAME, create_model, INITIAL_DOWN_SAMPLING
)
```


"Where's the latest code?" so I pushed the current code for now.


---
This page is auto-translated from [/nishio/ppoi改善2021-02-05](https://scrapbox.io/nishio/ppoi改善2021-02-05) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.