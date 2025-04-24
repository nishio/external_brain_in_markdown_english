---
title: "RAKE"
---

- Rapid Automatic Keyword Extraction (RAKE)
- [Automatic Keyword Extraction from Individual Documents](https://www.researchgate.net/publication/227988510_Automatic_Keyword_Extraction_from_Individual_Documents)

    - [[stopword]] as a delimiter, then count co-occurrences within that fragment.
    - Fragment = candidate key phrase
- Calculate word scores
    - Number of places divided by frequency of occurrence
        - The use of co-occurrence graph ranks is a technique that was used in graph-based keyword extraction prior to TextRank.
    - Higher scores for "words that tend to occur in longer fragments."
        - Bias to emphasize idioms
            - [[Bias for longer key phrases to be selected]]
        - Can I interpret this as average fragment length?
- Calculate the score of a fragment
    - Sum of scores of words containing
        - Is it okay if it's Japanese?
    - This is the "quantity of meaning" scale
        - A Simpler Way
            - The amount of information a token has is set to 1.
            - This would rate a long key phrase.
        - I'm using the number of tokens divided by the frequency.
            - This is not clear.
            - If there is no overlap, the score is simply the square of the keyword candidate's token length
            - It is simply a theory that both rank and frequency are values that increase with frequency, and that dividing cancels that effect.
        - I can think of a way to use the IDF or something like that.
        - Although it is a concept that English speakers do not have, one can also think of kanji as having more information per character and hiragana as having less.
                - [[RAKE Experiment 1]]
            - Aren't there a few keywords that consist only of hiragana?
            - Analyzing Wikipedia titles?
                - Parentheses should be removed.

- If two keywords appear more than once in the same order, a key phrase is created that also includes the stop word in between.
    - If there is a copy and paste string, will it be selected?
    - The fact that the score of a fragment is the sum of the scores of its elements is the reason why the score remains the same even when a stopword with a score of 0 is inserted
        - In fact, the score should go down depending on the number of stopwords.
    - [[RAKE stop list generation]]
    - looks pretty good

- For example, on "The Intellectual Production of Engineers
    - The "of" is a stop word, so it gets chopped first.
    - The word "engineer" is [[It's one word, so the score will be lower.]]
        - I'm not so sure it needs to be a rank number in the sense of "the longer the more important the bias," so it might as well be a string length.

- This keyword extraction and "dividing into stickies" to cut out information in larger units can be realized with an algorithm that has basically the same structure, perhaps with different parameters.
- SentencePiece seems to perform better as an internal representation during machine learning, but as output for the human eye, it seems better to chop with a dictionary in MeCab for more convincing word boundaries [[RAKE Experiment 1]].
    - Low barrier to using part-of-speech information, etc. because of the use of MeCab.
    - One disadvantage of MeCab is that tokens alone cannot be restored to the original string.
        - Because information on whitespace characters between tokens is lost.
        - As for this, the root is the same, even if the tokens are aligned in lower case and can't be put back.
        - Considering the bundling of verbs and nouns, information about appearance and information expressing meaning should be managed separately.
        - A [[doc2vec]]-like vector representation might be a better form of semantic representation
- The RAKE algorithm uses a stop list generated from Wikipedia with a high of 1000 pages.
    - Many deep learning-like methods require huge data, and the annotation cost is a hurdle that makes it difficult to tailor learning to individual company domains, but RAKE may be able to do it.
    - RAKE uses a 0/1 stop list to create the candidate set, and then uses almost only word counts to score the keyword likeness, which leaves a lot of room for ingenuity and the use of part-of-speech information by using MeCab.

[[Keyword Extraction]]
- [[keyword extraction]]
---
This page is auto-translated from [/nishio/RAKE](https://scrapbox.io/nishio/RAKE) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.