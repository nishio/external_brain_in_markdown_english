---
title: "How Link Suggestions/Transversal Ambiguous Searches Work"
---

- Mechanism of [[link suggestion]]/crossing [[ambiguous search]] 2020-10-02

What is Link Suggest/Cross-ambiguous search?
- Temporary name for a recently created prototype
- Derived from the project "[[keyphrase extraction]]", but the name doesn't match the image.
- Between recommendation and search, it behaves like this

link suggestion
- Recommendation Aspects
- The "link" here is not an HTML a-tag thing.
    - Scrapbox-like links
    - ![image](https://gyazo.com/74d958772afcf77278aff64833dbbb58/thumb/1000)

- How it differs from a mere recommendation
    - I know the reason for the recommendation.
    - Difference between recommendation of "documents that may be relevant" and suggestion of links to "documents in which common key phrases appear".
    - ![image](https://gyazo.com/ee555b5172594de522479f8c518fcb87/thumb/1000)
    - For example, suppose that a seemingly unrelated statistics article is recommended for an article on DX (true story).
        - Recommendations that don't show a reason make me wonder, "Why is this article relevant?" and twisting your head.
        - People tend to be uncomfortable with things they don't understand
        - Link Suggest shows "The keyword "dx" is common! and the human can laugh it off and say, "No, that dx is part of the integral! and the human can just laugh it off.

Cross-sectional ambiguity search
- Search Aspects
- When I made it, it ran faster than expected.
- Immediate results for human input
    - →Search-like
- When viewed as a search, it is "a system that enables ambiguous searches across many documents.
- For example, if you have a lot of digitized books, a cross search can make it easier to find the source of "I read that somewhere" and discover unexpected connections between multiple books.
    - I used to convert PDFs to text and search them with ag, but this is an exact string match, so it's easy to miss or output a large amount of text.
    - In this prototype, we put in a long query and look for the longest match.
    - Rather than entering keywords to search, you can enter a fragment of a document you are currently writing and search for related books.
- ![image](https://gyazo.com/d9ab2df57c4f6d8dd19dd47ca8234cd4/thumb/1000)

structure
- suffix array
    - input string
        - `seq = "abc-abc$"`
:
| i | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 |
| -- | -- | -- | -- | -- | -- | -- | -- | -- |
| seq | a | b | c | - | a | b | c | $ |
        - 100 million characters
    - output (e.g. of dynamo)
    - All "strings after the i-th character of seq" sorted in lexicographic order
sa
| i | sa |
| -- | -- | -- | -- | -- | -- | -- | -- | -- | -- |
| 0 | 7 | $ |
| 1 | 3 | - | a | b | c | $ |
| 2 | 4 | a | b | c | $ |
| 3 | 0 | a | b | c | - | a | b | c | $ |
| 4 | 5 | b | c | $ |
| 5 | 1 | b | c | - | a | b | c | $ |
| 6 | 6 | c | $ |
| 7 | 2 | c | - | a | b | c | $ |

- Letters and Words
    - Being in character is not a requirement.
    - Any sequence of values that can be compared large and small.
    - If you inscribe a word and then assign a word ID to it, you can use it for word strings as well.

- Suffix sequence construction costs
    - A naive sorting gives O(N log N)
    - Using the SA-IS method, suffix sequences can be constructed with O(N)
    - Explaining the SA-IS method would take an hour or two by itself.

- LCP array
    - longest common prefix
:
| i | sa | lcp |
| -- | -- | -- | -- | -- | -- | -- | -- | -- | -- | -- |
|    2 | 4 | 3 | a | b | c | $ |
|    3 | 0 |  | a | b | c | - | a | b | c | $ |
    - For example, in this section, three letters are common
        - longest common prefix is 3 characters
    - The worst-case calculation is O(N^2), but it can be reduced to O(N) (Kasai method).

- Search mechanism: O(M log N) in a binary search of the array
    - M is the query length
sa
| i | sa |
| -- | -- | -- | -- | -- | -- | -- | -- | -- | -- | -- |
| 0 | 7 | $ |
| 1 | 3 | - | a | b | c | $ |
| 2 | 4 | a | b | c | $ |
| 3 | 0 | a | b | c | - | a | b | c | $ |
| 4 | 5 | b | c | $ |
| 5 | 1 | b | c | - | a | b | c | $ |
|  |  | b | c | d | e |  |  |  |  | query |
| 6 | 6 | c | $ |
| 7 | 2 | c | - | a | b | c | $ |
    - For example, if we search for "bcde", we first look at number 3 in the middle, then number 5 because it is larger than that, then number 6 because it is larger than that, and so on, and we know that it falls between 5 and 6 because it is smaller than that.
    - Since N is 8, we can find the longest matching position in $\log_2 8 = 3$ times
        - →Exploratory Topic: Using LCP sequences, it is possible to make O(M+log N)

- How Link Suggestions Work
    - Perform a binary search from the start of all long queries
        - bcde → bcde cde ed e
        - Equivalent to performing a search on all subword sequences
    - fast enough
        - A query is about 10,000 characters and takes about 1 second to search.
        - A few tens of milliseconds for normal use.

- Obtaining the number of occurrences per document
    - LCP with the query can be obtained by comparing before and after after binary search
        - That is, this is "the longest possible common string between the query and the documents to be searched."
        - ![image](https://gyazo.com/68175d7d532835370e65e142c04daa7f/thumb/1000)
    - By creating the LCP array in advance, the number of occurrences of that common string can be counted.
    - The suffix array can be used to determine the location of occurrences of that common string.
    - If an array of document breakpoints is prepared in advance, a dichotomous search can be performed to determine which document each occurrence is in by O(log D), where D is the number of documents.
    - →Exploratory topic, there is an algorithm that can efficiently compute statistics for the entire document by using LCP sequences. We have considered it, but this time we only compute for matches. It seems that loading the result of the previous calculation into memory is more expensive than the cost of the calculation after the match.

- Discrimination of search results
    - If you put out all the hits, you get information overload.
    - Appropriate rules and scoring need to be put in place to make the selection.

- How Ambiguous Searches Work
    - Convert word appearance to digest value pairs at the timing of word segmentation, and perform word identity judgment on the digest value.
    - For example, if you set the conjugated form of a verb to the original form when you digest, it will ignore the conjugation and match
    - If you skip particles such as "of," "share information," "share information," "share information," etc., it will also match.
    - I'm not doing it now, but for example, if you group synonyms and thesauruses into the same digest value, you can absorb that swing.
        - It can be done mechanically by using a [[word2vec]]-like method to make a vector and then using the k-means method, but if you do too much, you lose the advantage of "knowing the reason for the recommendation".

- experiment
    - Suffix array created from PDFs of 834 books
    - Linear at 180,000 characters per second of build time
:
| books | docs | chars | load | translate | construct | chars / construct |
| -- | -- | -- | -- | -- | -- | -- |
| 10 | 3028 | 1567704 | 0.06 | 5.92 | 8.34 | 187974 |
| 100 | 30799 | 19774115 | 0.39 | 84.9 | 125.86 | 157111 |
| 834 | 264166 | 177638808 | 3.69 | 729.6 | 1130.48 | 157135 |
    - translate is the process of morphological analysis and digest into a sequence of word IDs
    - Cross-searching from 834 books to about 250 ms for a document of about 140 characters per Tweet.

![image](https://gyazo.com/7f2414c42a84ac48981813c3d473b6af/thumb/1000)

![image](https://gyazo.com/c699b8503916a26e59516de79a17868e/thumb/1000)

---
This page is auto-translated from [/nishio/リンクサジェスト/横断曖昧検索の仕組み](https://scrapbox.io/nishio/リンクサジェスト/横断曖昧検索の仕組み) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.