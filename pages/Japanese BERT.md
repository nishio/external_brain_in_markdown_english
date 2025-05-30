---
title: "Japanese BERT"
---

In using [[BERT]] in Japanese, there is a person who distributes a re-trained model because the model published by the original Google has a problem in handling Japanese. Thank you very much.

- [BERT Japanese Pretrained Model - KUROHASHI-KAWAHARA LAB [http://nlp.ist.i.kyoto-u.ac.jp/index.php?BERT%E6%97%A5%E6%9C%AC%E8%AA%9EPretrained%E3%](http://nlp.ist.i.kyoto-u.ac.jp/index.php?BERT%E6%97%A5%E6%9C%AC%E8%AA%9EPretrained%E3%) 83%A2%E3%83%87%E3%83%AB]
    - > Input text: All Japanese Wikipedia (about 18 million sentences)
    - > Morphological analysis is performed on the input text using Juman++ (v2.0.0-rc2), and then [[BPE]] is applied to split the text into subwords.
    - Paper [https://www.anlp.jp/proceedings/annual_meeting/2019/pdf_dir/F2-4.pdf](https://www.anlp.jp/proceedings/annual_meeting/2019/pdf_dir/F2-4.pdf)
        - Reasons for not using SentencePiece:.
            - > It is also possible to use sentencepieces and the like for raw sentences without morphological analysis, but the parsing unit may shift significantly during parsing.
    - Slides [https://speakerdeck.com/tomohideshibata/nlp2019-bert-parsing-shibata](https://speakerdeck.com/tomohideshibata/nlp2019-bert-parsing-shibata)

- [BERT with SentencePiece trained and model published in Japanese Wikipedia - theoretically possible - a blog, or rather a miscellany, of people in the data analysis community. [https://yoheikikuta.github.](https://yoheikikuta.github.) io/bert-japanese/]
    - Repository [https://github.com/yoheikikuta/bert-japanese](https://github.com/yoheikikuta/bert-japanese)
        - I think it's the same guy as [[Cookpad + BERT]], but this one is trained on Wikipedia as the source data.
        - I guess they couldn't release anything using Cookpad's internal data.
        - Using [[SentencePiece]].

- [Publication of Sentence Distributed Expression Model with Large Japanese SNS Corpus : Distribution of hottoSNS-BERT | Hotlink, Inc.](https://www.hottolink.co.jp/blog/20190311-2)
    - 86M Tweets trained on the original data.
    - Using SentencePiece

[[BERT]]

---
This page is auto-translated from [/nishio/日本語BERT](https://scrapbox.io/nishio/日本語BERT) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.