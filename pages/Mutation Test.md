---
title: "Mutation Test"
---

- Using mutpy
    - [https://pypi.python.org/pypi/MutPy/0.4.0](https://pypi.python.org/pypi/MutPy/0.4.0)
- Creating a miscellaneous unittest to use mutpy
- If you're writing in Series 2, you need to make it Series 3, so we'll do something like 2 to 3.
python

```
import doctest
from unittest import TestCase
import core

def load_tests(loader, tests, ignore):
    tests.addTests(doctest.DocTestSuite(core))
    return tests 

class SameOutputTest(TestCase):
    def test_output(self):
        import subprocess
        out = subprocess.check_output("python entrypoint.py --algo=algo2 --data=data/data6.csv", shell=True)
        self.assertEqual(file('test_output.txt').read(), out)                                                                                 
```



`mut.py --target core --unit-test test_geister -m -r report.yaml > log.txt`

---
This page is auto-translated from [/nishio/Mutation Test](https://scrapbox.io/nishio/Mutation Test) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.