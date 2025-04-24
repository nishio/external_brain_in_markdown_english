---
title: "Recovery when working from buggy output"
---

- The buggy program transformed the original data A to create B.
- This conversion is of the type that rewrites some lines of A
- B is assumed to override A
- I noticed the bug after working on the overwriting for a while based on B.
- What to do?
- ![image](https://gyazo.com/c05c70b00516bf7fea67a00a02440d42/thumb/1000)

- First, retrieve the original data A from Dropbox version control
- Commit to Git (so that you can immediately return to A)
- Commit B, commit C
- Eliminate bugs in the program to create the correct conversion result D from the original data A
- Cherry-pick C after committing this D
![image](https://gyazo.com/52acc25cdd3c54d9c404a641bcd82e3e/thumb/1000)
- This will lead to a "manual correction C for the correct conversion".
- Some conflicts occur and we will fix them.

---
This page is auto-translated from [/nishio/バグった出力を元に作業した場合のリカバリ](https://scrapbox.io/nishio/バグった出力を元に作業した場合のリカバリ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.