---
title: "Setting up pytest in VSCode"
---

I have no idea.
I used to call pytest as a module, not as a command, so I tried to specify the same thing, but I get an error with no details.
.vscode/settings.json

```json
{
  "python.pythonPath": "venv/bin/python",
  "python.testing.pytestPath": "venv/bin/python -m pytest",  // here
  "python.testing.pytestArgs": [
    "tests", "--cov=server", "--cov-report=xml"
  ],
  "python.testing.unittestEnabled": false,
  "python.testing.nosetestsEnabled": false,
  "python.testing.pytestEnabled": true
}
```


Then, I tried to insert a shell script like this, but the result was also not clear
bash

```
#!/bin/bash
python -m pytest $* --cov=server --cov-report=xml
```


[python - Imports break VSCode testing with pytest - Stack Overflow](https://stackoverflow.com/questions/57273945/imports-break-vscode-testing-with-pytest)
Here's the workaround.
tests/__ini__.py

```
import sys
sys.path.insert(0, ".")
```


So we can now test it with GUI.

I wonder if this is useful?
If only some of the tests are run, of course, the areas not covered by them will "not pass the test" in terms of coverage.
It might be better to bundle the tests for coverage output into a shell script and not output coverage when running the tests from VSCode.

[Testing Python in Visual Studio Code](https://code.visualstudio.com/docs/python/testing)

---
This page is auto-translated from [/nishio/VSCodeでpytestの設定](https://scrapbox.io/nishio/VSCodeでpytestの設定) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.