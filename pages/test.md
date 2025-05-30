---
title: "test"
---

- [pytest: helps you write better programs — pytest documentation](https://docs.pytest.org/en/latest/)
    - [Getting started with Python unit testing with pytest and pytest-mock - Qiita](https://qiita.com/ninomiyt/items/8db897c42c551e926c0f)
- [mutmut · PyPI](https://pypi.org/project/mutmut/)
    - You can apply it to all of them at once, but it might be better to do COVERAGE first to reduce the number.
        - [Coverage.py — Coverage.py 5.0a6 documentation](https://coverage.readthedocs.io/en/latest/)
        - Since it is obvious that mutations in the untested range will not be detected by the test
        - Over 300 detections were made in mutmut, and information flooding
        - Rather than looking at individual mutations and thinking about how to cover them, it would be better to first take a quick look at what areas are not covered by the coverage html.
        - → down to 16 pieces.
        - The -t option on the command line is used to test the test mechanism, but the argparse part is included in the coverage and the test is rewritten with the values of the various options.
    - Interesting detection
        - I used to fix random.seed for test repeatability when I used to use random.choice, but now I don't use random numbers anymore. mutmut pointed out to me that "changing the random seed makes no difference in test results!"
- `# pragma: no mutate`

---
This page is auto-translated from [/nishio/テスト](https://scrapbox.io/nishio/テスト) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.