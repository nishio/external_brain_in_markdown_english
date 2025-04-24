---
title: "call PyPy"
---

python

```
import subprocess
import sys
if sys.argv[-1] != "DONTCALL":
  subprocess.call("pypy3 Main.py DONTCALL", shell=True)
  sys.exit()
print("hello, pypy!")
```

[https://atcoder.jp/contests/abc177/submissions/16407994](https://atcoder.jp/contests/abc177/submissions/16407994)

---
This page is auto-translated from [/nishio/call PyPy](https://scrapbox.io/nishio/call PyPy) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.