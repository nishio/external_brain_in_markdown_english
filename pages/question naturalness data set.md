---
title: "question naturalness data set"
---

from [[pKeicho-done]]

Implemented earlier for questions that do not take keywords and questions that do take one.
The question that takes two is mada.

-----
- Data 1: 600 questions taking 0 to 1 keywords
- Data 2: (unused) 6,000 cases under the same conditions as Data 1
- Data 3: Active learning, using data 1 to train the model and selecting only those with 0.1 to 0.9
- Data 4: Question text that takes two keywords, with one of them filled in with an X

question naturalness data set
- Human input
- Questions about it
- Unnatural (0)/Natural (1)/Blank (0.5)
- Distressed(1)/Not distressed(0)

The training data was gathered in a haphazard way, so the training part was created.
- feature value
    - body (of a machine)
    - context (of a passage)
    - position of appearance
- I forgot to include it in the original data template.
    - Keyword, Question ID
        - Let's just output this one and paste in an additional one.
- feature generation
    - Keyword Body Features
    - Search input by keyword to find the first occurrence
    - take up a position with
    - For questions where keywords are not present, use the entire sentence and the beginning and end of the sentence.
- Now I'm asking all the questions for a random choice of sentences.
    - That's why there are so many of them.
    - I made 600 cases, but the amount of original text is 13.
- Right now, the input text is fixed, and the keywords in it are selected to make question candidates.
    - But with this, what happens if the keyword doesn't exist in the input, or if the keyword is there but it's not good (like "w").
        - Should there be an option to say "(go through this input and ask a question about the previous input)"?
- Active learning next?
    - If the ones that are deemed not good enough are no longer used, we won't be able to collect training data.
    - Trade-offs between use and exploration
        - Let's just cut corners and go with Epsilon Greedy.
    - →I set it to [[active learning]] for now and just discarded <0.1 and 0.9<.

---
This page is auto-translated from [/nishio/質問自然度データセット](https://scrapbox.io/nishio/質問自然度データセット) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.