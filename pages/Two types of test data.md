---
title: "Two types of test data"
---

![image](https://gyazo.com/4fc110db69fe29797a5784e731d72264/thumb/1000)
- The test data for A are all OK or at least one NG in the current state.
    - Testing to make sure you are not unintentionally breaking a function that was working.
    - Everything is OK, that's the normal state of affairs.
    - A lot of ng will puncture a human being.
    - Add one test case that goes to NG, then implement it so that it goes to OK.
    - This gives me peace of mind that I can fix it.
- Test B is a test that describes the ideal state
    - If everything is OK with the current situation, we are not meeting our objectives.
    - I get a lot of NG.
    - It is inherently difficult for humans to grasp the entirety of the NG case.
    - So observe statistics such as the percentage of correct answers.
    - Once enough of this type of test data is accumulated, machine learning can be used.
    - Often, because it is difficult to create B test data from scratch, it is created by reworking only the strange parts of the program's output
    - It's based on the assumption that "the program doesn't behave ideally" to begin with.
- Don't mix A and B.
    - Using a mixed bag as an A, we are crushed by a large number of NGs that we don't know how to remedy.
    - Using a mixture of the two as B, machine learning will focus on maintaining the status quo instead of approaching the ideal.

---
This page is auto-translated from [/nishio/2種類のテストデータ](https://scrapbox.io/nishio/2種類のテストデータ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.