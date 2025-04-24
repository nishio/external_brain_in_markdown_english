---
title: "PDF to Scrapbox"
---

2023-09-12
There are many situations where you want to use PDF as a starting point for intellectual production support
- I've tried many things in my life.
- As of 2023, the development of LLM has led to a feeling of "I want to unify all the things I've been doing by patching things together, and I want to make it easier to update.

[[**There are two ways to PDF]]
- Cutting and scanning from books (hereafter: scanned PDF)
    - This includes the images on each page in high resolution
- Lecture materials such as PowerPoint (hereafter: slide PDF)
    - This contains images of the material, not of each page

## PDF to page image
.
- Some say that using [[pdfimages]].
    - But [[pdfimages]] is a command to retrieve images in PDF in lossless mode, so if you use it for a slide PDF, you will not get an image of the page
- In that case, you can use [pdftocairo
    - Reference: [[PDF to PNG conversion]].

## PDF to text
.
- Text can be obtained by [[OCR]] from an image.
- Slide PDFs can be extracted with [[PDFMiner]], etc. with cleaner text than with OCR.
- However, the same text is obtained from "book PDFs with embedded OCR results" as well
    - This is of lower quality than today's OCR, depending on the level of technology at the time of embedding.
        - [[OCR Accuracy Comparison 2018]]
    - Even if you have an old OCR-embedded PDF, it would be better to ignore it and OCR it with the new [[Google Cloud Vision]].
- Google Cloud Vision is $1.5 for 1,000 cases in the high zone.
- [[Gyazo Pro]] costs 490 yen/month
    - Internally, Google Cloud Vision

## text and images are paired and managed
.
- Even if there is a hit in a search for a text, there are times when you want to see the paper because you can't make sense of the text alone or you want to see a diagram, etc.
- In the past, a text file with one line of text per page was prepared for each PDF and searched in a grep-like manner, and the number of hit lines was displayed, which was used to open the PDF.
- As of 2023, I do not think it is good that intellectual production can only be done in front of a PC. I want to use it while taking a walk or taking a bath. When I think about it, I want to put it in a cloud environment, not in a local environment on my PC.
- 2023-09-13 [[Gyazo Pro]], I thought, why not?
    - 2023-09-14 I actually tried it and got `Too many requests` after about 10,000.
    - Since the acquisition of OCR results is also included in the API call, only about 6,000 pages can actually be processed per day.

## 1:N correspondence between books and images
.
- Machine-readable data is spit out as JSON and sent to Dropbox
    - Make it possible to get it via API if you feel the need.
- Data on Scrapbox is edited by humans as they wish.

## Static content to dynamic process
.
- [[PDF]] to [Scrapbox
    - [[active reading]]

## Scrapbox and content correspondence
.
- Put all PDF pages in one Scrapbox page
    - A page should be a unit of meaning, especially a page in a book is not a unit of meaning
- Put all PDFs in one project
    - Unexpected connections are the source of value.


__BELOW_IS_AI_GENERATED__
# PDFからScrapboxへ
 2023-09-12 23:26 <img src='https://scrapbox.io/api/pages/nishio-en/omni/icon' alt='omni.icon' height="19.5"/>
### Summary of notes
.
We are exploring ways to utilize PDF for intellectual production support. there are two types of PDF, scanned PDF and slide PDF, and it is important to understand the characteristics of each. pdftocairo] is useful for retrieving page images from PDF, and [[OCR]] and [[ PDFMiner]] are available for text extraction. PDFMiner] can be used. However, the accuracy of OCR has been improving due to technological advances, and OCR results with the newer [[Google Cloud Vision]] are of better quality than older OCR results. By managing text and images as a pair, it is possible to refer to the paper from the search results. Gyazo] is effective for this. We are also looking to move from static content to a dynamic process.

### Relation to Fragment
.
The fragment "OCR" is related to the "PDF to Text" section of the note and confirms the excellent performance of Google Cloud Vision's OCR. Also, "Interference with bylines" is an important factor affecting the accuracy of OCR. The "Figure Extraction" section is relevant to the Note in that it explores ways to extract figures from scanned PDFs and use them for intellectual production. The "[[20180408Note on task abstraction sticky note]]" is related to the "Pairing and managing text and images" section of the notebook and highlights the importance of page-by-page text extraction and retrieval.

### deep thinking
Through Notes and Fragments, we were able to think deeply about how PDFs can be used to support intellectual production. In particular, we felt that it is important to pursue the improvement of efficiency and quality of intellectual production in terms of text and image pair management, improved text extraction through advances in OCR, and the transition from static content to a dynamic process.

### summary of thoughts and title
.
"The Evolution and Potential of PDF-Based Intellectual Production Support."
The use of PDF for intellectual production support continues to evolve, and it is important to explore its potential from a variety of perspectives, including text and image pair management, advances in OCR, and the transition from static to dynamic.

### extra info
TITLES: `["OCR", "Figure Extraction", "20180408 task abstraction sticky note", "What to do when knowledge output is required that cannot be copied and pasted", "Hatena2009-10-02"]`
generated: 2023-09-12 23:26
---
This page is auto-translated from [/nishio/PDFからScrapboxへ](https://scrapbox.io/nishio/PDFからScrapboxへ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.