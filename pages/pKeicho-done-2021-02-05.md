---
title: "pKeicho-done-2021-02-05"
---

[[pKeicho-done]]
pKeicho-done-2021-02-05
- Create a statistics script for logs
    - Script to download logs, only those that are not local.
    - skip:  [[IGNORE file to exclude inappropriate items from the analysis]]
    - [[QNF]], obviously heavy since it's following the whole word-question pair.
    - If it can't be the best, we decided to prune the branches before calling the question naturalness determination.
    - [[Copy at the touch of a button without having to select and copy all when exporting to Scrapbox]]
- I want to download data from Firebase.
    - →Statistics for the data were created without downloading, downloading is just a cache and should not be done until it is needed.
    - I did it because I needed to.
        - Enables statistics and testing with logs
            - [Don't ask questions related to keywords you haven't dug into.
            - Take human input from logs and use a new algorithm to examine changes in behavior.
        - Hitting the local cache update script will download all data that has not yet been downloaded locally.
        - Statistics, etc. for the whole can be done locally only.
            - [[Replay ✅ past logs with keyword extraction results at that time]]
    - [[Motion Extraction]]
    - Extraction of movements (key phrases containing verbs)
        - Binary classification, active learning to create training data and multilayer perceptron
        - Play what is inconvenient on a rule basis.

- Server doesn't know when it's at 500.
        - [[Indicate if it is taking a long time or if it is an error]]
- The places that require a certain number of keywords to be extracted are triggered quickly.
        - [[Coordination of state transitions]]


- Redesigned so that questions that do not take keywords can calculate scores with environment as an argument

- Modified to not ask relationship questions for keywords that have not been delved into.
- Copy button on Scrapbox export screen
- NG Keyword Judgment
    - I don't have enough data to learn, so I'll play a list of bad words I see.

    - [[Explicitly tell users when keyphrase extraction speed is slow]]

---
This page is auto-translated from [/nishio/pKeicho-done-2021-02-05](https://scrapbox.io/nishio/pKeicho-done-2021-02-05) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.