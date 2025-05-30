---
title: "Text extraction from PDF"
---

2023-09-12
- Let [[Gyazo Pro]] take care of everything, including mapping text and images and putting them in the cloud.

2023-04-07
    - [[PDF to PNG conversion]] and then use [[Google Cloud Vision]] API (planned)
    - The decision that it is better to charge than to create noisy data with free tools and work harder later.

2022-03-29 3-line summary:.
- `$ pip3 install pdf2txt.py`
- `$ pdf2txt.py -V -o <outfile> <infile>`
- I'm thinking of making a new script, so I'll add the details when it's ready.

2020-09-28 3-line summary:.
- `$ pip install pdfminer.six`
- `$ pdf2txt.py -V -o <outfile> <infile>`
- [https://github.com/nishio/ja_pdf_to_text](https://github.com/nishio/ja_pdf_to_text)
    - [[ja_pdf_to_text]], [[PDFMiner]]

2018-09-24 1-line summary: clone PDFMiner.six repository, generate CMap, then setup.py install

When I wrote [[Natural Language Processing with word2vec]] before, I used [PDFMiner](https://www.unixuser.org/~euske/python/pdfminer/).
I had been using the scripts from that time for mere text extraction, but I wanted to try various new things.
As of 2018, PDFMiner only supports Python 2, so use [PDFMiner.six](https://github.com/pdfminer/pdfminer.six), which supports 2/3.

summary
- I want to use PDFMiner.six because I want to use it with Python3
- CMap generation is necessary to handle Japanese PDFs
    - I don't know how to generate it when installing with pip, so I clone it from the repository.
    - It says to `make cmap`, but it says `make: Nothing to be done for cmap.
    - Explicitly hit the command written in the Makefile (below) #CMap re-generated
        - Maybe I could have done make cmap_clean, but I haven't tried it.
- `$ python setup.py install`
    - If you piped it in first, uninstall it.
- `$ pdf2txt.py -V -o <outfile> <infile>`
Now you get a clean text file.

remarks
- With [[pdftotext]], which is bundled with [[poppler]], the conversion appears to be straightforward, but there is an unintuitive disorder in the line order. (Perhaps the confusion is caused by irregular bounding boxes such as footnotes or chapter headings at the end of the page.)

CMap generation command
sh

```
python tools/conv_cmap.py -c B5=cp950 -c UniCNS-UTF8=utf-8 pdfminer/cmap Adobe-CNS1 cmaprsrc/cid2code_Adobe_CNS1.txt
python tools/conv_cmap.py -c GBK-EUC=cp936 -c UniGB-UTF8=utf-8 pdfminer/cmap Adobe-GB1 cmaprsrc/cid2code_Adobe_GB1.txt
python tools/conv_cmap.py -c RKSJ=cp932 -c EUC=euc-jp -c UniJIS-UTF8=utf-8 pdfminer/cmap Adobe-Japan1 cmaprsrc/cid2code_Adobe_Japan1.txt
python tools/conv_cmap.py -c KSC-EUC=euc-kr -c KSC-Johab=johab -c KSCms-UHC=cp949 -c UniKS-UTF8=utf-8 pdfminer/cmap Adobe-Korea1 cmaprsrc/cid2code_Adobe_Korea1.txt
```



sampling example
![image](https://gyazo.com/ace0fa36a067600a48c2ea4e4b9391db/thumb/1000)
Results in PDFMiner after cmap generation
> Purpose of this book
>
>  I want a good reference book on intellectual production techniques. I teach intellectual production techniques to others.
>  I would like to have a book that I can recommend when I am in the market.
>  I have been engaged in intellectual productivity research at Cybozu for 10 yearsNote 1.
>  As part of my duties, I organize my thoughts and ideas at the Kyoto University Summer Design School.
>  I have conducted workshops on how to make outputs, and I am also a part-time lecturer at Tokyo Metropolitan University.
>  As an instructor, I teach university students about creating new knowledge through research.

Failure log under -----

Result with PDFMiner put in by pip
> Purpose of this book
>
>  I(cid:888), Intellectual Production Techniques(cid:887)Good(cid:845)Reference(cid:853)Greed(cid:864)(cid:845)(cid:880)(cid:866). People(cid:884)intellectual production techniques(cid:923)teaching(cid:849)(cid:916).
>  (cid:881)(cid:854)(cid:884), (cid:851) recommendation (cid:906)(cid:880)(cid:854)(cid:916) book (cid:853) greed (cid:864)(cid:845)(cid:880)(cid:866).
>  I(cid:888),(cid:945)(cid:928)(cid:984)(cid:930)(cid:950)(cid:880)intellectual productivity(cid:887)research(cid:884)10 years engaged(cid:864)(cid:879)(cid:854)(cid. 903)(cid:864)(cid:872)(cid:2987)1. Industry
>  Duties(cid:887)part(cid:881)(cid:864)(cid:879), Kyoto University(cid:945)(cid:986)(cid:660)(cid:963)(cid:946)(cid:928)(cid:1007)(cid:949)(cid:939)( cid:660)(cid:999)(cid:880), 考(cid:849)(cid:923)整理(cid:864)(cid:879)(cid:926)
Hmmm, you're embedding CID fonts. [[CID problem]]

This is what happens with [[pdftotext]] bundled with [[poppler]].
> Purpose of this book
>  I want a good reference book on intellectual production techniques. I teach intellectual production techniques to others.
>
>  I would like to have a book that I can recommend when I am in the market.
>  I have been engaged in intellectual productivity research at Cybozu for 10 yearsNote 1.
>  As part of my duties, I organize my thoughts and ideas at the Kyoto University Summer Design School.
>
>  I have conducted workshops on how to make outputs, and I am also a part-time lecturer at Tokyo Metropolitan University.
>  As an instructor, I teach university students about creating new knowledge through research.
>
>  I have tried to communicate. However, in the limited time we have, we cannot convey what we want to say.
>  I want a book that summarizes what I want to say in one volume. I would like to have a book that contains all my messages in one volume.
>  But I don't have just one good book to recommend. If I could recommend just one book, it would be Kawaki.
>  "Ideas" Note 2, but this is a book from 1966. The abstract idea is now
>  Denjiro's
>
>  Purpose of this book
>
>  No, I don't. If you introduce a lot of reference books, they will not all be read.
It may look good at first glance, but the last line, "No, I don't. Even if I introduce a reference book, I can't convey what I want to convey in the limited time" is a continuation of "I can't convey what I want to convey in the limited time" eight lines above. The sequence of "Kawaki," "Tanjiro's," and "'Idea' Note 2" is also incorrect.

The same ranges are properly aligned in PDFMiner.
>  I have tried to communicate. However, in the limited time we have, we cannot convey what we want to say.
>  No, I don't. If you introduce a lot of reference books, they will not all be read.
>  No, I can't. I would like to have a book that contains all my messages in one volume.
>  But I just don't have the right book. If I could recommend just one book, it would be Kawaki.
>  "Idea Method" by Jiro TadaNote 2, which is a book written in 1966. The abstract idea is now
>  > The specific methodology is based on the technology level of 50 years ago, though it is valid enough.

- [[PDFMiner Coordinate System Analysis]]
---
This page is auto-translated from [/nishio/PDFからのテキスト抽出](https://scrapbox.io/nishio/PDFからのテキスト抽出) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.