---
title: "Cut out the part of interest"
---

    - [[direct quotation model]]
    - Similar to [[attention mechanism]], but attention itself needs to be fed back to the human
    - [[Viterbi algorithm]] used in [[hidden Markov model]]
    - [[Sentence granularity]]
    - I need something a little longer than keyphrase extraction.
    - I want it to be natural as "[[speech]]."
    - With key phrases, it's too short.

- It's a little tricky when it's [[ppoi]]-based.
    - Multiple discriminators are trained from a single data set.
    - It's a big deal to create the data naively, because it's an identification task for each character in a sentence.
        - 280,000 lines
        - Interactive mode is slow.
        - Downsampling implemented.
    - I took the 5 letters before and after each point and put them in unknowns, but most of them are negative examples, and it's hard to make a teacher out of just 5 letters.
    - Is this a pattern that requires making some teachers in advance?


---
This page is auto-translated from [/nishio/注目部分を切り出す](https://scrapbox.io/nishio/注目部分を切り出す) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.