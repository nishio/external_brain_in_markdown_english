---
title: "Rare CID problem"
---

- The [[CID problem]] was solved with [[CMap regeneration]], but the phenomenon of rare characters being replaced by CID still occurs.
If this is the case as it is, a frequent word could be `cid`.

solution
- Simply delete
    - Fill in [character-based language model
- Manual entry for each book

I tried to display one book, but it was surprisingly small, so I entered the correct answer by hand.
python

```
data = data.replace("(cid:12101)", ":")
data = data.replace("(cid:31)", "fi")
data = data.replace("(cid:7743)", "progress")
data = data.replace("(cid:29)", "fl")
data = data.replace("(cid:30)", "ff")
data = data.replace("(cid:13949)", "rabbit")
data = data.replace("(cid:7656)", "翰")
data = data.replace("(cid:7767)", "nada")
data = data.replace("(cid:12255)", "●")
data = re.sub(r"\(cid:12[678]\d\d\)", "", data)
```

I wonder if the correspondence between codes and letters is the same for other publishers. Probably not.
The last line is squashed together because there are many CID embeds that are not shown below. This is surely a watermark to identify who leaked the PDF when it was leaked.
>  engineering knowledge(cid:12705) target(cid:12710)(cid:12684) raw(cid:12699)(cid:12674) industry(cid:12693)(cid:12755) art(cid:12696)(cid:12741)(cid:12708)

---
This page is auto-translated from [/nishio/レアCID問題](https://scrapbox.io/nishio/レアCID問題) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.