---
title: "OCR Accuracy Comparison 2018"
---

from [[OCR]]
OCR Accuracy Comparison 2018
2018-10-27
[[Bookscan]] creates PDFs with OCR applied, so I didn't really consider the details, but the OCR performance of [[Google Cloud Vision]] was far superior.

Interference with side lines
- ![image](https://gyazo.com/67101158807d5b29809390f890103ba3/thumb/1000)
- > (Bookscan) The second book, also by Katsuhiko Eguchi, is a management philosophy based on various memories of Konosuke. How can we succeed?
- > (Google) The second book is "The Law of Success: Why Konosuke Matsushita Succeeded" (PHP Factory Publishing), also by Katsuhiko Eguchi, who wrote his management philosophy based on his many memories of Konosuke. How can we succeed?
- The part I drew a byline because I thought it was important has become OCR garbled and spoiled the electronic value of the document.

Horizontal characters in vertical text
- ![image](https://gyazo.com/eac37d8f5b0f1d981ea041bb13eaf9fe/thumb/1000)
- > In December, the company turned profitable in a single month, and by March of the following year, monthly sales exceeded ¥10 million. The method of sharing information within a company using web technology was called "intranet," and many companies were experimenting with its use. This is what it means to be in step with the times. Cybozu 038," created by Mr. Hata, is much easier to use than existing groupware, making it easier to share information. Cybozu 038" sold faster than the three of us had expected.
- > In February, Cybozu became profitable in a single month, and in March of the following year, monthly sales exceeded 10 million yen. Many companies were trying to introduce "intranets," a method of sharing information within a company using Web technology. This is what it means to be in step with the times. Cybozu Ofce," created by Mr. Hata, is by far easier to use than existing groupware, and it is easy to share information. Cybozu Ofce" sold faster than the three of us had expected.
- Bookscan recognizes "Cybozu OB8", "Cybozu 038", "Cybozu 00hoi", and Mathematically
- Google's has consistently been "Cybozu Ofce".
- Better to be mistaken for one "Cybozu Ofce" than to be converted into another one of each.
    - I can fix it with replacements.
- A hard-to-detect mistake on Google's part, "It says February when it's really October and December," is occurring.
    - When using statistical methods to complete from the surrounding string, the numbers are often wrong.


---
This page is auto-translated from [/nishio/OCR精度比較2018](https://scrapbox.io/nishio/OCR精度比較2018) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.