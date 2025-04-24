---
title: "Import is moved before sys.path setting in VSCode"
---

Imports are moved before the sys.path setting due to [[autopep8]] in [[VSCode]] and cannot be imported.
Just do `nopep8`.
python

```
sys.path.append("../bert")
import modeling  # nopep8
```



---
This page is auto-translated from [/nishio/VSCodeでsys.path設定より前にimportが移動される](https://scrapbox.io/nishio/VSCodeでsys.path設定より前にimportが移動される) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.