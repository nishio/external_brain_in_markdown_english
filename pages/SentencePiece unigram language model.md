---
title: "SentencePiece unigram language model"
---

About the unigram language model of [SentencePiece
- ![image](https://gyazo.com/60c096fa001c7a81578e8c1e99c021e7/thumb/1000)
- [[subword regularization]] : Neural Machine Translation with Multiple Candidate Subword Segments [[Taku Kudo]] 2008
- [http://www.anlp.jp/proceedings/annual_meeting/2018/pdf_dir/B1-5.pdf](http://www.anlp.jp/proceedings/annual_meeting/2018/pdf_dir/B1-5.pdf)
- For example, if there is a string ABC and the lexical set contains each letter and AB, and if $p(AB) > p(A)p(B)$ holds, then the division "AB/C" has a larger p(x) than the division "A/B/C".
- And with this method, you have to give V in advance, so you start with a large enough vocabulary and prune away.
    - ![image](https://gyazo.com/3de118fd9537e450c1e530d352ddf00d/thumb/1000)

Subword regularization: Improving neural network translation models with multiple subword candidates. In Proc. of ACL.
[https://aclweb.org/anthology/P18-1007](https://aclweb.org/anthology/P18-1007)

SentencePiece: A simple and language independent subword tokenizer and detokenizer for Neural Text Processing
Taku Kudo, John Richardson (Submitted on 19 Aug 2018)
[https://arxiv.org/abs/1808.06226](https://arxiv.org/abs/1808.06226)

---
This page is auto-translated from [/nishio/SentencePieceのユニグラム言語モデル](https://scrapbox.io/nishio/SentencePieceのユニグラム言語モデル) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.