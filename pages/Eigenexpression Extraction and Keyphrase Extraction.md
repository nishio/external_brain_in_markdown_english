---
title: "Eigenexpression Extraction and Keyphrase Extraction"
---

![image](https://gyazo.com/bf9ee01e448c03397c463e522060c2b3/thumb/1000)
- [series labeling
    - [[Eigen-Expression Extraction]] labels the "beginning of the eigenexpression" and the "range of eigenexpressions".
    - The [[RAKE stop list generation]] algorithm in [[keyphrase extraction]] counts the number of times a word is "in" or "next to" a keyphrase.
    - Mapping to series labeling would be labeled "keyphrase range" and "keyphrase adjacency".
    - Personally, I think it would be better to distinguish between "right neighbor" and "left neighbor".

Which labeling is better?
- As for keyphrase extraction, I think it's more straightforward to label around the latter keywords.
- What do humans do when they explicitly state that a sentence is indistinguishable from a ground sentence and "it's a keyword"?
    - For example, enclose in brackets
    - Conversely, even if other conditions are the same, the probability of a key phrase being a key phrase is naturally increased in the area enclosed by brackets.
    - With the latter labeling, the " " token naturally corresponds to "the label to the left of the keyword.
- What is the reason why eigenexpression extraction often uses the former labeling?
    - Eigenexpression may be contiguous.
    - The method of labeling the perimeter is impossible.

PS
![image](https://gyazo.com/0d4a9b4df47f33e77eceeb1fb27b739a/thumb/1000)
- I was comparing 2-1 and 3, but there are more detailed steps.
- 4 can identify consecutive keywords.
- 5 can distinguish "words that do not appear at the end of keywords but often appear within keywords" such as "of

- [[start/end labeling]]

---
This page is auto-translated from [/nishio/固有表現抽出とキーフレーズ抽出](https://scrapbox.io/nishio/固有表現抽出とキーフレーズ抽出) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.