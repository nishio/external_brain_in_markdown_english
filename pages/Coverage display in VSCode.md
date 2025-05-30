---
title: "Coverage display in VSCode"
---

![image](https://gyazo.com/35e8e3c2157682f333552cd16c84fb2a/thumb/1000)
Install: [Code Coverage Highlighter - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=brainfit.vscode-coverage-highlighter)
`$ python -m pytest <target-test-file> --cov=<source-dir> --cov-report=xml`
Cmd+Shift+P: Code Coverage: Toggle coverage display
![image](https://gyazo.com/5de6b0ef98ef282cd81d67c0b9d601ba/thumb/1000)

It looks like pytest-cov was included with [[pytest]] when it was installed.
- I saw an article by someone who tried it with unittest, but the coverage report format is the same, so I guess it works either way.

I'm looking at coverage.xml, not .coverage.
- If you remove this, the highlight will disappear, and if you update it, the highlight will be updated as well.

If you don't limit it with `--cov=<source-dir>`, it tries to output coverage of all the contents of external libraries as well, and it's heavy.

The Git diff view was also highlighted and chaotic.

- [[Setting up pytest in VSCode]]

---
This page is auto-translated from [/nishio/VSCodeでカバレッジ表示](https://scrapbox.io/nishio/VSCodeでカバレッジ表示) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.