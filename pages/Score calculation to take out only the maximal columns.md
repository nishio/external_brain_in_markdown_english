---
title: "Score calculation to take out only the maximal columns"
---

![image](https://gyazo.com/7e76fe3268f150e9b8451b69efa249b1/thumb/1000)
- When a series has a score of 0 or 1, if you consider the ranking of "the product of the scores for a subsequence", it includes all the subsequences of the interval that are 1.
- If you interpret the algorithm in [[RAKE]] to mean that the columns from which stopwords are removed are candidates for key phrases, with a score of 0 for stopwords and 1 for everything else, this approach is incorrect because it also includes sub-columns.
- If we consider that the outer scores of the subcolumns are multiplied by the score subtracted from 1, only the extreme columns will have a score of 1
    - This fits well with the concept of the [[RAKE stop list generation]] algorithm, which counts the number of adjacent occurrences of a key phrase

- I think this all comes down to the [[hidden Markov model]].
    - Hidden state is either 2 states of "being a keyword, not a keyword" or 4 states of "not a keyword, before a keyword, within a keyword, after a keyword".
- If it can be attributed to hidden Markov, then it can also be attributed to [[conditional probability field]].
        - [[series labeling]]

---
This page is auto-translated from [/nishio/極大列だけ取り出すスコア計算](https://scrapbox.io/nishio/極大列だけ取り出すスコア計算) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.