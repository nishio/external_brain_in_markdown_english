---
title: "Commands to enable copying PDFs that do not allow text copying"
---

> [hikalium](https://x.com/hikalium/status/1951764685134667895) A command to make a PDF copyable (effectively equivalent to "print as PDF") where the PDF itself is publicly available but text copying is not:
>  gs -dNOPAUSE -dBATCH -sDEVICE=pdfwrite -sOutputFile=hoge_copy_enabled.pdf hoge.pdf
>  (PDF must still be destroyed...)

[[PDF]]

---
This page is auto-translated from [/nishio/テキストコピーができないPDFをコピー可能にするコマンド](https://scrapbox.io/nishio/テキストコピーができないPDFをコピー可能にするコマンド) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.