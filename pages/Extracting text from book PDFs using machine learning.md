---
title: "Extracting text from book PDFs using machine learning"
---

What we've done so far #book scanned PDF
- Textualized versions of books contain page numbers, footnotes, and various other strings.
    - Initially, I thought [[line continuation judgment]] would identify whether text is directly connected or connected with intervening whitespace, but I was wrong.
- Need a mechanism to identify "what is this" on a line by line basis for information on one page
        - [[Page Row-Based Language Models]]
    - At first, I was thinking of creating a language model-like form of learning, but when I wrote a rule-based model as a sample, it was surprisingly easy to create.
- This worked well when I tried it in "The Engineer's Art of Intellectual Production", but when I used it in "The Art of Exploration of Knowledge", I didn't get any text at all.
    - The former is indented with full-width spaces at the beginning of paragraphs, while the latter is not, so
- Rather than modify the rule-based version, we decided to make it machine learning.
    - I made one line as a baseline, assuming that the input would be five lines, plus two lines before and after, and it worked well enough.
            - [[OCR Garbage Cleaning]] may be required separately
- Added on 2018-10-18:.
    - The idea of "5 lines with a line before and after" is like [[textCNN]], but [[Transformer]] is more interesting in many ways.
    - The row feature vector is not made from the word [[embedded vector]], similarly the page feature vector should be made
            - [[Automatic generation of table of contents]]
![image](https://gyazo.com/696b82b79dce69112dd3cbaabe29cb23/thumb/1000)
- Convert text converted from PDF to feature vector as one item per line (output-features)
    - Set of 4 lines: rows, features, labels, and blank lines
- A human looks at it and assigns a label as appropriate.
- Active-learning based on the learning data
    - Output "labeled features", "their labels", and "features that are not confident in their identification" in json
        - It's active learning for multi-class classification, so it's sorted by the difference between first and second place.
    - learned model
- Merge
    - Merge the original data with the training result data.
    - In fact, you can add new features here, since they are newly re-created without using the output-features feature.
    - Use unique pageRatio, lineRatio pairs to link to existing data
    - Output merged results to honbun_merged_features.txt, diff to make sure there are no major problems, then manually rename to honbun_features.txt
- Main text output (output-honbun)
    - Extract the main text from the learned model and the feature data.


Minimum Procedure
- --output-feature to create feature vector
- --output-honbun --use-model to specify intellitech/honbun_model.npz
- Look at the resulting honbun.txt file, and if it looks OK, OK.


---
This page is auto-translated from [/nishio/機械学習による書籍PDFからの本文抽出](https://scrapbox.io/nishio/機械学習による書籍PDFからの本文抽出) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.