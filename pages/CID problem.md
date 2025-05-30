---
title: "CID problem"
---

I installed PDFMiner with pip to extract text from a Japanese PDF and the following problem occurred.
> I(cid:888), Intellectual Production Techniques(cid:887)Good(cid:845)Reference(cid:853)Greed(cid:864)(cid:845)(cid:880)(cid:866). People(cid:884)intellectual production techniques(cid:923)teaching(cid:849)(cid:916).
Solution: see [[Text extraction from PDF]].

-----
Notes on the research process
- [Still have issues with CID Characters · Issue #39 · euske/pdfminer](https://github.com/euske/pdfminer/issues/39)
    - 2014
    - Pointing out that [[CMap]] needs to be reworked.
- [pdfminer - PDF text extraction returns wrong characters due to ToUnicode map - Stack Overflow](https://stackoverflow.com/questions/28678841/pdf-text-extraction-returns-wrong-characters-due-to-tounicode-map)
    - 2015
    - Talking about [ToUnicode map
- [python - What to do with CIDs in text extracted by PDFMiner? - Stack Overflow](https://stackoverflow.com/questions/50773909/what-to-do-with-cids-in-text-extracted-by-pdfminer)
    - Talking about ToUnicode map
- [How can I extract embedded fonts from a PDF as valid font files? - Stack Overflow](https://stackoverflow.com/questions/3488042/how-can-i-extract-embedded-fonts-from-a-pdf-as-valid-font-files)
    - Can embedded fonts be extracted? Discussion
- [Extracting Japanese text from PDF with PDFMiner](https://qiita.com/korkewriya/items/72de38fc506ab37b4f2d)
    - Reports of two-point stools and others being replaced by CID
- [I tried to use Python to extract text data from PDF (pdfminer.six) - Arakan "BOKU"'s IT Daily Life](http://arakan-pgm-ai.hatenablog.com/entry/2018/01/07/080000)
    - 2018
    - Example of importing and using from within a script rather than from the command line
    - This one, like my environment, has hiragana as CID.
---
This page is auto-translated from [/nishio/CID問題](https://scrapbox.io/nishio/CID問題) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.