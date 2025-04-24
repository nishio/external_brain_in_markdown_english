---
title: "PDF to PNG conversion"
---

Related: [[Text extraction from PDF]].

2023-04-07
- It's been five years since I last put this together, so I asked GPT4 for recommendations.
- GPT4's answer to cut-and-scan PDF: [[PyPDF2]].
    - This will be `KeyError: '/XObject'` for some PDFs.
    - It would be an error if the image was not embedded, as in the 2017 summary below.
- GPT4 answers about General PDF: [[pdf2image]].
    - `$ pip install pdf2image`
    - It uses [[pdftocairo]] internally, pdftocairo is a tool of [poppler
    - `$ brew install poppler`
python

```
    from pdf2image import convert_from_path
    images = convert_from_path(pdf_path)
    for i, image in enumerate(tqdm(images)):
        image.save(os.path.join(output_dir, f"{i+1}.png"), "PNG")
```

    - Example of output
        - ![image](https://gyazo.com/e475b087b9ff628e9d78baa62758e604/thumb/1000)
        - 72dpi by default

2017-08-23
- summary
    - gs has terrible image quality, ImageMagick(convert) also uses gs internally. pdftoppm is better, but [[pdftocairo]] is the best.
        - `pdftocairo -r 200 -f 0 -png mybook.pdf prefix`
    - As for the cut scan PDF, the cleanest way is to extract the -r 300 equivalent image embedded in pdfimages.
        - The problem is that we need to decide if it is that kind of PDF or not.
    - The quality of pdftocairo is almost the same as pdfimages. But 48 times slower.

- gs
    - `$ time gs -q -dBATCH -dNOPAUSE -sDEVICE=png16m -r100 -sOutputFile=pages_%04d.png mybook.pdf`
    - `gs -q -dBATCH -dNOPAUSE -sDEVICE=png16m -r100 -sOutputFile=pages_%04d.png   219.36s user 5.22s system 95% cpu 3:54.68 total`
    - 552x823
    - ![image](https://gyazo.com/c9f7451a31da4c565fd3ef0b10f784bf/thumb/1000)![image](https://gyazo.com/307ffe755412681e1de74d138b4b2832/thumb/1000)
    - Terrible jaggies.

- pdftoppm
    - `$ time pdftoppm -r 100 -png mybook.pdf mybook`
    - `pdftoppm -r 100 -png mybook.pdf mybook  464.95s user 6.77s system 96% cpu 8:07.62 total`
    - 552x823
    - ![image](https://gyazo.com/cfda2fb38aebcfdc7cbc6d6de3b34303/thumb/1000)![image](https://gyazo.com/6e07e92a8638865780d6aa54dc2cb3cf/thumb/1000)
    - much better

- pdftoppm Output at twice the resolution
    - `$ time pdftoppm -r 200 -png mybook.pdf mybook`
    - `pdftoppm -r 200 -png mybook.pdf mybook  1104.28s user 12.22s system 96% cpu 19:14.59 total`
    - 1104x1646
    - ![image](https://gyazo.com/790a870887bba282ad6bb12d1d869bff/thumb/1000)![image](https://gyazo.com/4e31fcad5aba227fc490bf350a00f962/thumb/1000)
    - Has the atmosphere of the title changed a lot? (Thinner? Sharper impression)
    - After doubling the size, the thumbnail above is reduced to twice the size. Does the text become thinner in the process?

- So what would happen if you put it out at twice the resolution on the gs?
    - `$ time gs -q -dBATCH -dNOPAUSE -sDEVICE=png16m -r200 -sOutputFile=pages_%04d.png mybook.pdf`
    - `gs -q -dBATCH -dNOPAUSE -sDEVICE=png16m -r200 -sOutputFile=pages_%04d.png   619.65s user 13.83s system 93% cpu 11:14.36 total`
    - ![image](https://gyazo.com/9ce844ae4f2c48c58dcc300e916b0f1f/thumb/1000)![image](https://gyazo.com/39f68f800e536c4b268bda4213c5396c/thumb/1000)
    - dirty
    - Mincho font "Hen" horizontal strokes, etc. are missing.
    - Enlargement (left: gs, right: pdftoppm)
    - ![image](https://gyazo.com/7d3d0371af344c56ee8ce7ddfa66f05d/thumb/1000)
    - gs seems to sample only once per pixel. pdftoppm looks like a behavior of sampling and mixing several times.

- ImageMagick(convert)
    - `$ time convert -verbose -density 200 mybook.pdf pages_%04d.png`
    - `"gs" -q -dQUIET -dSAFER -dBATCH -dNOPAUSE -dNOPROMPT -dMaxBitmap=500000000 -dAlignToPixels=0 -dGridFitTT=2 "-sDEVICE=pngalpha" -dTextAlphaBits=4 -dGraphicsAlphaBits=4 "-r200x200"  "-sOutputFile=/tmp/magick-le3ab9PT-%08d" "-f/tmp/magick-s7CciX7v" "-f/tmp/magick-6huEpaq8"`
    - ![image](https://gyazo.com/9a73370c5cbcc45a1b740dc3e7f9267a/thumb/1000)![image](https://gyazo.com/c36f8d7fb55966b464c6397be100b506/thumb/1000)
    - As you can see from the command line output, it is hitting gs internally. The image quality is also similar to gs.

- pdfimages
    - `$ time pdfimages -j mybook.pdf ./pages`
    - `pdfimages -j mybook.pdf ./pages  6.14s user 2.51s system 59% cpu 14.569 total`
    - Extract image files in the target PDF
    - Since the experimental PDF is a cut scan of a paper book, the scan result is contained in an image file.
    - ![image](https://gyazo.com/112c27b96232c0d73b64c0c702265959/thumb/1000)
    - 1656x2469
    - The -r option for gs and pdftoppm was 552x823 when the -r option was 100, so -r 300 equivalent.
    - Try to reduce it to the same resolution
        - `$ convert -thumbnail 1104x1646 ex7/pages-002.jpg t.png`
        - `convert -thumbnail 1104x1646 ex7/pages-002.jpg t.png  3.86s user 0.09s system 98% cpu 4.002 total`
    - ![image](https://gyazo.com/ea73b2a3aefcc02a69a3ce949db11784/thumb/1000)![image](https://gyazo.com/317d4bf8891c5e1e60aa244cc5790c52/thumb/1000)
    - Pretty, but choose PDF origin

- pdftocairo
    - `$ time pdftocairo -r 200 -f 0 -l 10 -png mybook.pdf pages`
    - `pdftocairo -r 200 -f 0 -l 10 -png mybook.pdf pages  27.02s user 0.29s system 79% cpu 34.260 total`
    - ![image](https://gyazo.com/63792a9552169c1a0f71b15c69b10759/thumb/1000)![image](https://gyazo.com/8ec5f57781eea1a4e16f3ae8f118e26c/thumb/1000)
    - Enlarge (top left gs, top right pdftoppm, bottom left pdfimages and shrink, bottom right pdftocairo)
        - ![image](https://gyazo.com/3c493d7126c0692c284717ff2c536c19/thumb/1000)
        - Output almost equivalent to reduced from pdfimages
        - Not equal, but close enough that you can see the difference when you cut out one line and look at them closely side by side.
    - It took 34 seconds for 10 pages, which is relatively slow (19 seconds to produce 270 pages with pdftoppm, so roughly 48 times slower).

2017-08-23
---
This page is auto-translated from [/nishio/PDFからPNGへの変換](https://scrapbox.io/nishio/PDFからPNGへの変換) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.