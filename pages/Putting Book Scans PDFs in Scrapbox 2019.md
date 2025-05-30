---
title: "Putting Book Scans PDFs in Scrapbox 2019"
---

2019-10-08
- Place [[Book Scanning PDF]] in [Scrapbox
- [https://www.facebook.com/toshiyukimasui/posts/10157675595687498](https://www.facebook.com/toshiyukimasui/posts/10157675595687498)
    - [Gyazo](https://gyazo.com/api?lang=ja) There is a Gem
    - [masui/Book2Scrapbox: a device for reading self-prepared books in Scrapbox](https://github.com/masui/Book2Scrapbox)
- Upload to Gyazo Pro via script after disassembling into images
- Gyazo Pro uses Google Cloud Platform's [[CLOUD VISION]] API for [[OCR]].
- It takes time, so we get OCR data after a while.

Readings from [https://github.com/masui/Book2Scrapbox](https://github.com/masui/Book2Scrapbox)
- Scanning results from ScanSnap are retrieved in [[pdfimages]].
    - Related [[PDF to PNG conversion]].
    - If it's a cut-and-scan PDF, that's OK.
    - PDFs of slides, etc. are not acceptable.
- Locally, folders are cut and stored with MD5 hash.
- Sync it to AWS.
    - [AWS Command Line Interface (CLI: an integrated tool to manage AWS services)| AWS](https://aws.amazon.com/jp/cli/) must be installed
    - [Installing the AWS CLI - AWS Command Line Interface](https://docs.aws.amazon.com/ja_jp/cli/latest/userguide/cli-chap-install.html)
        - That's very kindly written.
    - [AWS CLI Configuration - AWS Command Line Interface](https://docs.aws.amazon.com/ja_jp/cli/latest/userguide/cli-chap-configure.html)
    - [[aws s3 sync]]
        - Deletion on hand does not delete anything on S3.
- Sync to AWS is not really required.
    - Because I'm sending the contents of the FILE to gyazo.
- [https://github.com/nishio/Book2Scrapbox](https://github.com/nishio/Book2Scrapbox)
    - Use [[pdftocairo]] since slides cannot be converted to images with pdfimeges
        - `$ pdftocairo -r 200 -f 0 -jpeg <pdf> pages`
            - see  [[PDF to PNG conversion]]
    - Multiple PDFs are now combined into a single JSON
    - pdfstojson.rb calls makejson.rb
        - I looked into how to do it in Python, but I was able to achieve it by using makejson.rb as a child process.
    - Download and add the OCR results from Gyazo a while after the JSON is ready.


[Facebook](https://www.facebook.com/nishiohirokazu/posts/10219634470988868)


---
This page is auto-translated from [/nishio/書籍スキャンPDFをScrapboxに置く2019](https://scrapbox.io/nishio/書籍スキャンPDFをScrapboxに置く2019) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.