---
title: "Only English letters are garbled."
---

![image](https://gyazo.com/f9added2b1a0d8a67793da8bec61af0f/thumb/1000)
[https://twitter.com/1t0t/status/1258273516006199296?s=21](https://twitter.com/1t0t/status/1258273516006199296?s=21)

This is what happens when a character code such as ISO2022-jp, which has an explicit character type switching code, mistakes an English character for a Chinese character because the switching code is lost for some reason.
Three of the characters included in the garbled text were matched, although they could not be reproduced completely by this method.
python

```
>>> "Ah Takayuki Itoh (ah ah)".encode("ISO2022-jp")
b'\x1b$B$"\x1b(BTakayuki Itoh(\x1b$B$"$"$"\x1b(B)'
>>> b'\x1b$B$"Takayuki Itoh(\x1b$B$"$"$"\x1b(B)'.decode("ISO2022-jp", "ignore")
'Ayo yeon gyeon jian ah)'
```


python

```
>>> b'\x1b$BTakayuki Itoh(\x1b$B$"$"$"\x1b(B)'.decode("ISO2022-jp", "backslashreplace")
'壤諱諱\x79\x75謇\x20\x49\x74\x6f recommended)'.
```


\\The only thing I can't figure out is how to make it into "zaki".
python

```
>>> "﨑".encode("ISO2022-jp")
UnicodeEncodeError: 'iso2022_jp' codec can't encode character '\ufa11' in position 0: illegal multibyte sequence
```

Hmm?

python

```
>>> "﨑".encode("ISO2022jp-3")
b'\x1b$(OOr\x1b(B'
>>> "﨑".encode("ISO2022jp-2004")
b'\x1b$(QOr\x1b(B'
```


- [[garbled text]]

---
This page is auto-translated from [/nishio/英字だけが化ける文字化け](https://scrapbox.io/nishio/英字だけが化ける文字化け) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.