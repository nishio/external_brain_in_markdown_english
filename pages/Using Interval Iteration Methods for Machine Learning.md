---
title: "Using Interval Iteration Methods for Machine Learning"
---

- Metaphor for cramming learning
    - You're given a problem and an answer, and you cram it.
    - Tests are given separately.
    - A lot of [[supervised learning]] now is this
    - Metaphor for [step-by-step procedure
    - Daily learning is the test.
    - Solve 100 questions in one session
        - Correct answers extend the interval between the next question by a factor of two.
        - Repeat questions that were answered incorrectly.
        - Mark 8 incorrect answers as unlearnable and remove them from the study.
        - Difficulty is automatically adjusted.
        - Datasets with too high a percentage of correct answers are boring.
        - Datasets with too low a percentage of correct answers are painful.
    - [[active learning]] in [[machine learning]]
    - Identifies data with no correct answer in the discriminator and assigns supervised data to those that are not confident in the identification results.

---
This page is auto-translated from [/nishio/機械学習に間隔反復法を使う](https://scrapbox.io/nishio/機械学習に間隔反復法を使う) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.