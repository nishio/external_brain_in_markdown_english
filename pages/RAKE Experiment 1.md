---
title: "RAKE Experiment 1"
---

[[RAKE]]
:

```
input:
I was looking at the Wikipedia dump data, and the link notation is a nice one token in SentencePiece, so I think I can use this. I'll have to do a lot of preprocessing, though.
```


SentencePiece / 100 document stoplist
:

```
output:
Link notation is sentencepiece: 81.00
wikipedia:      25.00
View dump data: 16.00
Becoming 1 token: 16.00
Various: 4.00
Pretreatment: 4.00
Also good: 4.00
Likely to be able to: 4.00
```


- "Link notation is S ent ence P ie ce".
- "W i ki pe dia"
- It's divided into 5 tokens, and "Wikipedia" is correctly bundled.
- The "law" is omitted from the stop list because of one token.
    - The stop list only uses about 100 pages of Wikipedia, so more could be on the stop list.
    - I want "link notation" to be a keyword in the first place, so SentencePiece's ticking may be inappropriate.
        - Maybe the token is too large because it is the one with vocab_size: 32000 that was used for the BERT Japanese model.

Mecab / 1000 document stoplist
:

```
Not good: 7.50
Not done: 4.50
Pretreatment: 4.00
Link notation: 4.00
So here it is: 4.00
Likely to be able to: 4.00
1 token: 4.00
In the name of: 3.50
but: 2.00
Hands: 1.50
Dump data: 1.00
Things: 1.00
Good: 1.00
wikipedia:      1.00
sentencepiece:  1.00
```


- I shouldn't, but I won't, so this, so I can."
    - This certainly doesn't look like much on Wikipedia.
- Other disappointments
    - Wikipedia and SentencePiece score lower.
    - With MeCab, [[It's one word, so the score will be lower.]]

Mecab / 1000 document stoplist / use average phrase-character-length instead of average pharase-token-length
:

```
I shouldn't have: 15.00
sentencepiece:  13.00
Link notation: 10.00
1 token: 10.00
Not done: 9.00
wikipedia:      9.00
So here it is: 8.00
Possible: 8.00
Pretreatment: 6.00
Dump data: 6.00
NAME: 5.00
but: 4.00
Hand: 2.00
Things: 2.00
Good: 2.00
```


---
This page is auto-translated from [/nishio/RAKE実験1](https://scrapbox.io/nishio/RAKE実験1) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.