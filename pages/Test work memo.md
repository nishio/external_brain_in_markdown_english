---
title: "Test work memo"
---

2021-01-25
    - [[Testing Policy]]
    - ![image](https://gyazo.com/d39aeaa66e75a16771389159cb5e2c3c/thumb/1000)
    - There seems to be a lot of different styles, like putting the test target in main, but I don't want to change it for testing because I'm using this structure to match the official documentation for deploying to Heroku.
    - python -m pytest` as root
        - see [[-m pytest]]
        - The current directory goes into sys.path, so you can do something like from server.keicho import process_command from the test code, straightforward.
    - You can also do `%run tests/test_foo.py` in ipython
        - You can use the test runner when you call it all together, but when you want to debug, you want to use the debugger.
    - Try individual test files with `python -m pytest tests/test_foo.py` and run them all when you're done.
        - Test cases that hit the server are heavy, and the server's behavior shouldn't change unless you deploy the modifications at hand in the first place.
    - When I did 2 of [[Testing Policy]], it behaved unexpectedly, which confused me, so I went deeper into it, testing 3 and 4 to find out the cause.
    - Bottom line, bugs put in at the time of porting.
    - For some reason, keyword extraction runs against the command as well."
    - Mistakes that refactor without testing and change behavior.
- Test Stability
    - There was supposed to be no random element, but in some cases the process of "choosing the largest score" resulted in the same score.
        - We've made it a little more cloggy for those who want to prioritize.

    - [[Coverage display in VSCode]]
    - [[Setting up pytest in VSCode]]

---
This page is auto-translated from [/nishio/テスト作業メモ](https://scrapbox.io/nishio/テスト作業メモ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.