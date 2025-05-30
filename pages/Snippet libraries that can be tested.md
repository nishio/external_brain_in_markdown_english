---
title: "Snippet libraries that can be tested"
---

- atcoder's talk on making it easier to reuse code you've written, now that it's taken shape, I'll put it into language [Twitter](https://twitter.com/nishio/status/1310549757778042882?s=20).
- The code I solved in the contest is the contest number and the file name is like abc123/e.py.
    - So, first copy this with an easy-to-understand name like libs/lazy_segtree.py.
- The code solved in the contest is designed to run local tests with -t, so it can be refactored while testing.
    - Separate the contest-specific code from the library-like code to be reused in preparation for reuse.
    - Put a marker with a comment in between.
- The snippet creation script reads libs/*.py and takes out only the library part and makes a snippet of vscode.
    - Make the first line of the docstring the snippet's explanatory text

Advantages of the Separate Marker Method
- Do not make the entire libs file a snippet
    - You can use the test code you wrote while participating in the contest without modification.
    - I don't want the test code to be copied and pasted when reused as a library.
    - If you put the library above the marker and the test code below, you can preserve the test code and not put it in the snippet.
    - Not only does it keep the small test at hand, but it also keeps it ready to submit to atcoder or aoj.
        - When you make a major change, you can submit it again to make sure it works.
        - You can also verify that the contest does not time out.

The contents of [this folder](https://github.com/nishio/atcoder/tree/master/libs) are converted to snippets in [this script [https://github.com/nishio/atcoder/blob/master/generate_](https://github.com/nishio/atcoder/blob/master/generate_) snippets.py] are converted into snippets

Libraries used in multiple contests gradually increase the number of test cases.
- The delayed propagation segment tree is just like that, and it now has test data from 7 contests on it.
- You can check to see if it is still in good enough condition to pass in each contest after modification.

Previous story.
[https://twitter.com/nishio/status/1309895501685297152](https://twitter.com/nishio/status/1309895501685297152)
- I have been thinking that I need to organize my segment tree code, but I haven't done it yet because I haven't yet come up with a good policy on how to maintain my own library for competition programming. If I make it into a module and import it for use, I would have to submit it as a single file, which would require a lot of copy and paste work afterwards, which would be tedious.
- I'm also thinking that it's better to paste it into the submission file from the beginning, since I have to rewrite it in a gory way to fit the problem conditions... And I think a vscode snippet is a good idea instead of "open file and copy and paste", but I'm still not sure how good that policy would be to do. I'm not sure.
- Another idea is to create a "data creation script for submission" that replaces the IMPORT statement. The good thing about this policy is that it should also be possible to turn off debug output or expand function calls inline during that conversion phase.
- The result of the conversion is put into the clipboard.

---
This page is auto-translated from [/nishio/テストできるスニペットライブラリ](https://scrapbox.io/nishio/テストできるスニペットライブラリ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.