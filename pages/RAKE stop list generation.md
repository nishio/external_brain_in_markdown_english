---
title: "RAKE stop list generation"
---

Stop list generation for [RAKE
- Words adjacent to but not included in the keyword are good candidates for [stopword
- Both precision and recall were improved by excluding from the stop list words whose frequency in the keyword is higher than the frequency adjacent to the keyword.
- F value is best with the largest stop list and could be made even better by making it larger.
    - The stop list made by DF alone is worse than the opposite.
    - Note that the training was performed on 1000 of the 2000 abstracts, and [[DF]] was tried on 10 or more, 25 or more, and 50 or more, respectively.
        - Interesting to use DF instead of TF.
impressions
- I see what you mean
    - I don't like the idea of splitting it into two values in a snap based on "more or less," but that's not the problem with this algorithm, it's the problem with the concept of stopwords in the first place.
        - Extending to the domain of probability, we can say that when a word is observed, the probability that it is part of a keyword and the probability that it is adjacent to a keyword
        - If a keyword is at the edge of a candidate, it is reasonable to think about whether to expand the candidate or not, and to say, "Let's not expand it because the probability of it being adjacent is higher.
        - Not when it's among the keyword candidates, right?
            - For example, "of" and "of" have a low probability of being present at the middle end of keyword candidates, but they are rather common in some of them.
            - So if it's overdivided, if it comes up more than once, it's rejoined, but I don't know if it's a good balance...
    - Each word has a "probability of being among the keyword candidates".
        - The stopword is it's zero, and the state it approximates.
            - Scores to be multiplied
        - Score for grammatical appropriateness of the keyword form
            - The score of a token sequence is calculated as the product of the scores of each token
            - State that this is 0/1 depending on whether this is a stop list element or not.
            - If it is a probability value, the more you multiply, the smaller it gets.
            - →Bias for selection of short key phrases
                - Offset by [Bias for longer key phrases to be selected

- If you have a "document with some keywords already marked up" like Scrapbox, you can get a stop list from there.

---
This page is auto-translated from [/nishio/RAKEのストップリスト生成](https://scrapbox.io/nishio/RAKEのストップリスト生成) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.