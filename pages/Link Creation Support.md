---
title: "Link Creation Support"
---

2019-10-30
- When content is mechanically poured into Scrapbox, it becomes a "[[warehouse of dead texts]]" because the crucial "[[link]]" is scarce.
- This is not the fault of pouring content: [[Machine Generated Scrapbox]].
- Lack of computer assistance for subsequent link creation is problematic
- So, for the sake of experimentation, we first created the following project
    - Convert PDFs of past lecture slides into one-page images
    - Images are uploaded to Gyazo and OCR results are retrieved
    - Create and import JSON so that one page is one page in Scrapbox
    - Pages 4000-6000
    - More Talk: [[Putting Book Scans PDFs in Scrapbox 2019]].
- Can you help create a link to this?

- Convert the text on each page into a 768-dimensional vector using [[BERT]].
- Experiment 1
    - Pre-implementation note: [[Classification by BERT]].
    - Take the first 12 dimensions of a 768-dimensional vector and create a 3-byte string with the positive and negative of the vector as 1 bit, and make it an empty link
    - Areas with identical 3-byte character strings (category codes) divide space equally into 2^12
        - It will be around 1 page per space.
    - Scrapbox can be equivalent to "hashtag classification" because pages linked to the same page are displayed together from that page.
    - result
        - [/nishio-a1/C, 4eb](https://scrapbox.io/nishio-a1/C, 4eb)
        - Slides with the same content used in different presentations are in the same category.
        - I'm not quite convinced what else is in there.
    - consideration
        - I guess I lost a lot of information because I mapped from 768 dimensions to 12 dimensions by simply ignoring the 756 dimensions.
        - For example, if you take 768 dimensions as input, compress them into 12 intermediate layers, and then finetune them with a network that identifies whether the two input slides belong to the same presentation, the intermediate layers will be reduced in dimension such that they are close in value in the same slide, and this is what you should use

- Experiment 2
    - From each of the 5744 pages, a link was provided to "the page that most resembles its content but is not equal to it".
    - The definition of "similarity" is SentencePiece+Japanese BERT converting a sentence into a vector of 768 dimensions, then Euclidean distance.
    - This page has slides from one presentation linked to slides from another presentation and linked from another presentation.
        - [/nishio-a2/f0f4390ca440,053](https://scrapbox.io/nishio-a2/f0f4390ca440,053) 2014 Nagoya University
            - →[/nishio-a2/8dec2e4bf848,060](https://scrapbox.io/nishio-a2/8dec2e4bf848,060) This is a f0f addendum 2014 Nagoya University addendum
                - ⇔[/nishio-a2/1add1c10ec2b,105](https://scrapbox.io/nishio-a2/1add1c10ec2b,105) leading to yet another addendum 2014 Nada High School Saturday Lecture Addendum
            - ←[/nishio-a2/3aaa60135699,027](https://scrapbox.io/nishio-a2/3aaa60135699,027) Simple writing slides 2018 Tokyo Tech CUMOT
    - Another example
        - [/nishio-a2/bd6c50dd861c,014](https://scrapbox.io/nishio-a2/bd6c50dd861c,014) A and B, with the heading A on the next page
            - →[/nishio-a2/bd6c50dd861c,019](https://scrapbox.io/nishio-a2/bd6c50dd861c,019) A link is generated to the page where the description of B begins
    - Another example
        - [/nishio-a2/bd6c50dd861c,010](https://scrapbox.io/nishio-a2/bd6c50dd861c,010) What is usefulness? From the slide "What is usefulness?
            - →[/nishio-a2/70b73cd8dc44,022](https://scrapbox.io/nishio-a2/70b73cd8dc44,022) Another presentation, "Useful to whom?" A link has been made to
        - "usefulness" and "useful" have no common parts in terms of strings, nor are they single tokens, so it's quite difficult to determine this as a similarity.


---
This page is auto-translated from [/nishio/リンク作成支援](https://scrapbox.io/nishio/リンク作成支援) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.