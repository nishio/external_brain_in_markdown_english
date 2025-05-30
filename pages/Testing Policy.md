---
title: "Testing Policy"
---

- Set up a local development server and hit it with HTTP
- Verify that the expected output is returned for the input
    - First, check the behavior for various commands
- User input may not contain keywords.
- Access Firebase to clear the memory of test users
    - Don't let your memory destroy the test.
- Download Firebase records if you want to test the internal state in the future.

![image](https://gyazo.com/47279ac9c3bdc365381c21b76e4f5836/thumb/1000)
- 0 is human operation
- 1 is an approach to automate browser operations
- 2 write a program in Python that interacts with the server using HTTPS instead of a browser.
- 3 run the server locally.
- 4 directly taps the server's internal logic in the same process.
- 5 replace Firebase with a mock and all in the same process.
    - There's also a way to mock up Firebase next to 3.
- The way to proceed this time is to do 2 lightly first, then move on to 3 and 4.

[[pKeicho]]

---
This page is auto-translated from [/nishio/テストの方針](https://scrapbox.io/nishio/テストの方針) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.