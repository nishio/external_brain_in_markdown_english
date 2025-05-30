---
title: "Key phrase extraction 2020-08"
---

Cybozu Labs Machine Learning Study Group

- [[keyphrase extraction]]
- Extract several short strings of less than one sentence from an input string longer than one sentence
- This time around.
    - Review (~[[TextRank]])
    - [[RAKE]]
        - [[concentration (of one's attention)]]

Word Frequency Approach
- Carve input into words
- Count the number of occurrences of each word.
- Score the "number of times".
    - This is called TF (Term Frequency)
- Showing the highest score

problem
- Frequent occurrence of words like "of" and "wo."
- This is a frequent occurrence in any text.
- I want to lower my score.

[[TF-IDF]]
- Count the number of documents in which the word x appears
    - Large DF words are "common" words
    - This is called [[DF]](Document Frequency)
    - So, the larger the DF, the smaller the score, which is TF-IDF
- (aside)
    - It is interesting to see a characteristic distribution for key phrases ([[concentration (of one's attention)]]) when plotted on two axes with DF2, "the number of documents in which the word x appears two or more times.
    - I'd take a log, but there doesn't seem to be much theoretical support for it.
    - Affected by average number of words in "document," etc.
        - If you use books, is one document a "book" or a "page"?
        - If it's groupware, is it one post, one thread, one space?

general managers' committee issue
- The term "General Manager's Meeting" refers to a specific recurring event throughout this in Cybozu.
- But when chopped into words, they are divided into "book," "director," and "association."
    - It gets mixed up with "book" meaning "book" and "meeting" meaning "meeting" of other events.
    - Even if the word "director" was used with high frequency, it is difficult for a human being to think from it that you are talking about the General Manager's Association.
- If it is to be shown to humans, it is necessary to extract "sequences of multiple words" as key phrases

[[TextRank]](2004)
- "TextRank: Bringing Order into Texts"
- If you chop them into words and treat them discretely, you lose information about word order, which is not good.
- Then, a graph is created with words as vertices and adjacencies as edges, which is multiplied by eigenvalue analysis to obtain a score for each word.
    - Inspired by Google's PageRank, hence the name TextRank.
- Words in the top 1/3 of the score are concatenated if they occur consecutively in the source text
- problem
    - Q: Wouldn't high frequency words score higher?
    - A: Yes, so TextRank uses only nouns and adjectives (noun phrase approach).

Problems with the noun phrase approach
- Narrowing down the candidates too much
    - Neither "intellectual production techniques of engineers" nor "100 people, 100 different ways of working" can be key phrases.
    - The "Lean Startup" is carved in middle black.
    - Analysis of data from users who frequently use Scrapbox showed that 10% to 30% of key phrases contained non-noun adjectives -> [[Scrapbox Statistics 2019-2]].

[[RAKE]](2010)
- Rapid Automatic Keyword Extraction
- [Automatic Keyword Extraction from Individual Documents](https://www.researchgate.net/publication/227988510_Automatic_Keyword_Extraction_from_Individual_Documents)
- Same issues as Nishio.
    - I want to take out "axis of evil" as a key phrase.
- structure
    - 1: First, divide by the words in the stop list
    - 2: If key phrases appear in the same order, they are combined, including the words in between.
    - ![image](https://gyazo.com/f4483bde4be44d3391ad3d33d60e1105/thumb/1000)
- The key is how to make a stop list.
    - TextRank's noun phrase approach is equivalent to putting all but noun adjectives in the stop list

- [[RAKE stop list generation]]
- The paper tries two patterns six different ways.
    - Pattern TF:.
        - The idea that words that occur frequently are stop targets.
        - Use a lot of word DFs.
    - Pattern KA:.
        - The idea is that words that appear next to key phrases and do not appear easily in key phrases are stop targets.
        - If the number of occurrences in a key phrase is greater than the number of occurrences next to the key phrase, exclude it from the stop list
- result
    - KA is good all around.
    - In TF, increasing the number of stoplists decreases performance, in KA it increases it.
    - With KA, "words that also occur frequently in key phrases" don't make the stop list, so they can be increased.
    - ![image](https://gyazo.com/ff40bc46f5d69f64b8cd6577a5f215e2/thumb/1000)

benchmark
- Speed is significantly faster than TextRank
    - TextRank is heavy on solving large matrix eigenvalue problems.
- Accuracy is best in both F value and percentage of fit.
    - The conformance rate is the percentage of key phrases that the system determines to be key phrases that are actually key phrases.
    - TextRank methods have evolved in various ways since then: [[PositionRank]], [[EmbedRank]], and so on.

supplementary examination
- Assume that the key phrase is the range enclosed by the Wikipedia link notation `[[ ]]`.
- Generate stop list with 1000/2000 pages
- Key phrase extraction against 1000 other pages
- Example: [ampersand](https://ja.wikipedia.org/wiki/%E3%82%A2%E3%83%B3%E3%83%91%E3%82%B5%E3%83%B3%E3%83%89)
    - INPUT `ampersand (&amp;) is a symbol for the juxtaposition of the particles "...and...". It is a ligature of the Latin "et" and is easily recognized in the Trebuchet MS font as <FILE>. ampersa, "and per se and", means "and [the symbol which] by itself [is] and". ... `
    - EXPECTED `['symbol', 'Latin', 'ligature', 'Trebuchet MS', ... `
    - OUTPUT `['symbol which] by itself [is] and', 'ampersand (&amp;, English name', 'and per se and', 'Trebuchet MS font', 'and [', 'ampersand', 'parallel particle', 'ampersa', 'Latin ', 'FILE', 'understand', 'symbol', 'display', 'meaning', 'ligature', 'et', ... `
    - `Precision: 0.208, Recall: 0.808, F-measure: 0.331`
- Precision 0.32+-0.30 for 1000 pages
    - Roughly similar results to the paper were reproduced.
    - Large standard deviation
        - It may be due to the fact that the abstracts of the papers are generally of similar length, whereas the random pages on Wikipedia are of varying lengths.
    - small talk
        - I'm taking the top 1/3 of the paper.
        - Normally, Precision goes down as you increase it.
        - In this experiment, it went up the other way.
        - High scoring key phrases have a high probability of not being correct.

Comparison
- TextRank
    - Stop list: non-noun adjectives
    - Combining: if high scoring adjacent to each other
- RAKE
    - Stop list: compare inside and adjacent to key phrases
    - Combining: if they appear in the same order

Stop List Considerations
- Stop list can be regarded as a "string -> 0/1" function
- What is "chopping at the stop word?"
    - ![image](https://gyazo.com/cdaa7d86db568a4ea3bf72d6e90a31b6/thumb/1000)
    - The red part is 1-p and then "the product is 1."
    - Consistent with the comparison of "number of occurrences within a keyword" and "number of occurrences next to a keyword."
- Is 0/1 sufficient?
    - 's" and so on, in, but also adjacent to.
    - Unknown words are not on the stop list.
    - You don't want to have "tokens that shouldn't be in keywords" that appear infrequently.
- For example, if a URL is mixed in with the input
:

```
f noun,general,*,*,*,*,*
3 noun,number,*,*,*,*,*
b noun,general,*,*,*,*,*
1 noun,number,*,*,*,*,*
af noun,general,*,*,*,*,*
2 noun,number,*,*,*,*,*
daee noun,general,*,*,*,*,*
8 noun,number,*,*,*,*,*
e noun,general,*,*,*,*,*
942 noun,number,*,*,*,*,*
b noun,general,*,*,*,*,*
49 noun,number,*,*,*,*,*
adbb noun,general,*,*,*,*,*
2 noun,number,*,*,*,*,*
e noun,general,*,*,*,*,*
40 noun,number,*,*,*,*,*
f noun,general,*,*,*,*,*
0 noun,number,*,*,*,*,*
c noun,general,*,*,*,*,*
6746 noun,number,*,*,*,*,*
f noun, proper noun, organization,*,*,*,*
```


Proposal to make it a stochastic model
- future work
- [[CRF]]
    - Commonly used in morphological analysis itself and other series labeling
- "Two or more occurrences of a key phrase sequence" is a global feature not used in CRFs, etc.
    - How do I make this work?

Regarding keyphrase binding
- Now they don't care what kind or how many tokens they have, they're combining them anyway.
- `'Make a presentation \u3000\u3000↓ \u3000 (immediately after the action'`)
    - They are combined because they appear multiple times, but I don't want full-width spaces in the key phrase.
    - To begin with, the newlines are gone at the MeCab stage, but shouldn't the newlines be tokens that never enter the keyphrase?
- of tokens inserted between them "probability of appearing in a key phrase."


---
This page is auto-translated from [/nishio/キーフレーズ抽出2020-08](https://scrapbox.io/nishio/キーフレーズ抽出2020-08) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.