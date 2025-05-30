---
title: "direct quotation model"
---

- The model is that [[chatbot]] does not generate the conversation, but simply quotes a passage from a book or other source.

2018-09-30
- I was trying to do with learning.
- Changed the rule base to separate by brackets, curly braces, punctuation, etc.
- After all, the most frequent bad pattern is that "broken sentences" are produced, so I just used punctuation marks to separate them.
- If anything, it would make more sense for [[seq2seq]] to take this "one sentence" as input data and output it by shaving off the indicator words, etc.
    - Leave it bare as the initial value.
    - Word-based input, output empty string when word to be deleted
    - I mean, would you prefer a binary classification of "bare or deleted"?

-----
- Model of the quotation itself
- Model of citation starting point
- Model of Citation End Points

feature value
- Contains key phrase 1/0
- The word boundary, 1/0
- It is of moderate length. What is the definition of moderate?
- Punctuation immediately preceding 1/0

- The model for the start and end points should be something that can be computed using only local features.
    - Context of surrounding few words
- The appropriate length of the quotation can be made as a model of the quotation itself
- The model of the goodness of the quotation itself is made by LSTM.
- We can use both as probability models and then multiply them together.

---
This page is auto-translated from [/nishio/直接引用モデル](https://scrapbox.io/nishio/直接引用モデル) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.