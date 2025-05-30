---
title: "Key phrase extraction 2019-04-02"
---

Cybozu Labs Machine Learning Study Session 2019-04-05
- We'll look back at what we've done so far and then we'll talk about current issues and ambiguous searches.

- [[keyphrase extraction]]
- We've done a lot of things and we're going to take a look back and sort it out.
    - Pointwise Estimation by [KyTea
        - [[most significant substring]] approach
    - [[SentencePiece]]
    - [[TextRank]]
        - [[Phrase-based TF-IDF]]

KyTea
- A system that divides a string into words using pointwise estimation of whether a word is a word boundary or not.
    - [http://www.phontron.com/kytea/index-ja.html](http://www.phontron.com/kytea/index-ja.html)
    - [[LIBLINEAR]]
- <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>was tinkered with around January 2015.
- I was wondering if this could be used to estimate the boundaries of key phrases
- In the process of this study, <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/> understood the concept of [[Active Learning]] (01/30/2015).
- 2015/03/11
    - > I was writing about keyphrase extraction using KyTea at a machine learning workshop on Friday, and while I was writing, I got the feeling that I should do a dependency analysis....
- After this, Kaggle gets excited and pends for a time.

Review of April 2017
>  Try KyTea to do keyword extraction that is not word-by-word in MaCab.
>  The approach of trying to extract keywords with KyTea was not correct.
> > Problem with preparing sufficient training data
> I think it would have been better to add rule-based "words connected" to the morphological analysis by MeCab to the keywords.
> I'm working on a "MeCab chopped and then extreme substring" approach that's similar to that.

maximized substring
    - An approach that applies the idea of [[most significant substring]] to a sequence of words rather than a sequence of characters.
    - Extreme substring = a substring such that there is no other string that contains it with the same number of occurrences.
- There are algorithms that can extract substrings that appear repeatedly.
    - [Suffix array - Wikipedia](https://ja.wikipedia.org/wiki/%E6%8E%A5%E5%B0%BE%E8%BE%9E%E9%85%8D%E5%88%97)(SA-IS method)
    - All substrings that occur more than N times" and so on can be efficiently retrieved.
    - →A key phrase is a sequence of words that appears repeatedly, so this could be used.
- <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I was doing this around April 2017.

result
- I did indeed extract the long strings of words I was hoping for.
- But a lot of other things were extracted as well.
- Active Learning to learn "Does it look like a key phrase?" filter.
- Results of the experiment around April 2017
    - > Higher score (excluding teacher data)
    - >  "biological" (37 times, 88.0%) "synthetic inhibitor" (20 times, 88.0%) "medial temporal lobe" (28 times, 88.0%)
    - > Lower score
    - >  "will be (figure)" (5 times, 14.7%) "after" (6 times, 14.4%) "if" (5 times, 14.4%)
- After this, the Deep Learning course was so exciting that it was put on hold for a while.

Monday, May 1, 2017 17:32
Experiment with keyphrase extraction into Scrapbox
> Summary of experiments with each page of the book as the target object
>  ・ Chapter headings tend to be extracted as frequent key phrases
>  ・It is interesting that there are examples of key phrases included in chapter headings appearing together in different places than in the chapter.
>  ・Maybe we can combine the appearances on consecutive pages into one.
>  ・It is not good that you can't read the text even if you click the link and jump to the page of the target object.
>  ・Technically it is possible to embed the text there, or embed images of the page, but it is not copyrightable, so it cannot be published.
>  →You can try with "Presentation Slide PDF" which you own the copyright.
- 'All appearances on successive pages are combined into one.'
    - 2020 postscript, this is [[page-level DF]].
    - Not very useful since it is obvious that it appears repeatedly (foreshadowing).

word segmentation
- I used MeCab to split the words beforehand.
- Muddled in processing key phrases that contain blanks in a way that can properly restore the blanks.
- The question of whether the word segmentation approach is the right one to begin with...
- The Problem of Unknown Words

[[SentencePiece]]
- Language model-based tokenizer
    - Reversible Text Segmentation
    - Eliminates the problem of unknown words.
    - The concept of grammatical words is irrelevant.
- Use the suffix array to extract the top 1 million occurrences of substrings and then reduce the vocabulary.
- 2018/12/18
    - > When I plugged in a corpus of 1700 character types of "The Art of Intellectual Production of Engineers" and had it divided into 10000, it's good that it recognizes "The Art of Intellectual Production of Engineers" as a single unit of mass, etc.
    - But what comes out is of course "10,000 tokens that can express that sentence," so it takes some effort to pick out key phrases from them that are interesting to humans.
    - > Based on, valid, based on, output example, paste, room cleanup, too little, inexperienced, coding, supervise, shrink, history, finally, radar chart, continuous, Dutch, move near related, compare, top down, one dimensional reading experience, ▁ Bacon, double fast, wall, mountain, gentle, refactoring, photos, handy, technical review, professor, mature, pull out, seen in chapter, display code, SMART, gather all first
- After this, I started working on the English version of the Intellectual Production Techniques of Engineers, and once pending

[[PositionRank]]
- April 2019 (i.e., now)
- PositionRank (2017 paper)
    - Multiply the Google PageRank algorithm on a graph of word sequences.
    - So far, the same as in the previous study TextRank (2004)
    - A paper that says that when a modification based on the position of word occurrence was added to this, it won the TF-IDF type keyphrase extraction.
- I'm not sure why it works, so I implemented it from TextRank.

[[TextRank]]
- Create a graph based on word adjacencies and pagerank
- Eigenvalue decomposition by creating a dens matrix of transition probabilities
    - It takes a little over 1 second for 1000 vertices (MacBook)
- Naturally the Rank of many words and adjacent words will be higher?
    - →That's right, if you do it normally, the "ha" etc. would be higher.
- Original paper filters out all but nouns and adjectives
    - →Subtle, as [[Scrapbox Statistics 2019-2]] shows that key phrases containing other than nouns and adjectives are used about 10-30% of the time.

TextRank: What is your multi-word key phrase?
- This is ultimately a "score the words in some way" method
    - I'm using PageRank for that "method".
    - So how do you find key phrases that consist of multiple words?
        - The top 1/3 of the score is used as candidate key phrases, and if they are adjacent to each other in the source text, they are combined.
        - This could use some more work...
        - For example, "Lean Startup" is divided into "Lean" and "Startup" because the middle black is a symbol, but it seems that these can be connected regardless of what the score of the middle black is.

TextRank: good results if limited to nouns?
- > For, thing, like, where, it, if ...
- Frequent nouns are extracted as key phrases.
- Do you put them on the blacklist?
- I mean, IDF...

TextRank and TF-IDF
- After all, the great thing about TextRank is that it doesn't require anything other than the document to be processed.
    - I don't even need information about the IDF.
    - But you use language-specific knowledge to extract only nouns...
- In a kintone or Scrapbox-like use case, using information on high-frequency words is not a real problem.
    - I'd rather use "information from other texts" and especially with Scrapbox, "information from key phrases that have already been manually added.
    - I want to improve incrementally.

- [[Phrase-based TF-IDF]]
- Approaches to using tfidf
- A method in which the phrase score is the sum of the TF-IDFs of each word that makes up the phrase score
- Use only the longest noun phrase as a candidate key phrase.
    - [[Phrase-based TF-IDF: Application of Noun Phrase Analysis]] (2013), which employs a mechanism to assign scores not only to the longest noun phrase, but also to partial noun phrases
    - Better for longer sentences averaging 8,000 words, but worse for shorter sentences averaging 134 words

- [[The Problem of Too Large Links]]
- The use case for the Scrapbox link:.
        - [[It is not beneficial to join a link with many participants]]
        - [[Links to faraway places]] is good
    - Even if they don't connect, it's good because it gives room for future connections.
- in other words
    - If N is the number of participants in the link, does it cost 1/N to score?
        - This is almost the same idea as IDF, except instead of word Frequency, it is phrase Frequency
    - Define "far."
        - On Scrapbox, the link is already displayed as a link up to 2 hops away on the existing link.
        - It is preferable to link to a page 3 hops or more ahead that is not included there

- [[Links to faraway places]]
- In the case of Scrapbox, the distance between pages is determined based on the connection relationship of links
    - This is because links between contents are manually assigned in advance.
- Not so with use cases such as kintone?
    - Not really.
    - Each record in the app has a distance difference depending on whether it is the "same app" or not.
    - Data that has a hierarchical structure has a hierarchical inclusion relationship as a link to determine the distance.
- Consideration [[Auto Bracketing]].

- [[hierarchical]]

- [[Bitap Algorithm]]


What we cut down
- Even in Scrapbox, "other projects" and "newly added content" are distance ∞.
- Would you prefer a system that can discover links between these things?

---
This page is auto-translated from [/nishio/キーフレーズ抽出2019-04-02](https://scrapbox.io/nishio/キーフレーズ抽出2019-04-02) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.