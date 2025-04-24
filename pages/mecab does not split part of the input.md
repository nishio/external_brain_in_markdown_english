---
title: "mecab does not split part of the input"
---

If a URL is mixed in a sentence, for example, if it is simply split by [[MeCab]], the URL will be split as well.
For some applications, we want to process certain semantic structures in preprocessing so that MeCab does not split the range
You can use [Constrained Analysis](https://taku910.github.io/mecab/partial.html) to achieve this.

Example of division
python

```
INPUT = "URLs are mixed in the text, such as https://scrapbox.io/nishio/new"
mecab = MeCab.Tagger()
print(mecab.parse(INPUT))
```

output

```
Sentences Noun,General,*,*,*,*,Sentences,Bunsho,Bunsho
Middle noun, suffix, adverb possible,*,*,*,*,middle,chu,chu
ni particle, case particle, general,*,*,*,*,ni, ni, ni
Retrieved from " https noun,general,*,*,*,*
:// noun,subjunctive conjunction,*,*,*,*,*
scrapbox noun,general,*,*,*,*,*
.       Noun, subjunctive conjunction,*,*,*,*,*
io noun,general,*,*,*,*,*
/ noun,subjunctive conjunction,*,*,*,*,*
nishio noun,general,*,*,*,*,*
/ noun,subjunctive conjunction,*,*,*,*,*
new noun,general,*,*,*,*,*
Participle of,*,*,*,*,*,*,*,*, no, no, no
yo Noun, nonindependent, auxiliary stem,*,*,*,*,yo,yo,yo
to particle, adverbialization,*,*,*,*,*,ni,ni ...
```


Example of not splitting
python

```
mecab = MeCab.Tagger("-p")
INPUT += "\n"  # need to avoid segment fault
INPUT = re.sub(
    r"\s*(https://[-0-9a-zA-Z!#$&'()*+,/:;=?@\[\]._~%]+)\s*",
    r"\n\1\tURL\n", INPUT)
print(mecab.parse(INPUT))
```

output

```
Sentences Noun,General,*,*,*,*,Sentences,Bunsho,Bunsho
Middle noun, suffix, adverb possible,*,*,*,*,middle,chu,chu
ni particle, case particle, general,*,*,*,*,ni, ni, ni
https://scrapbox.io/nishio/new  URL
Participle of,*,*,*,*,*,*,*,*, no, no, no
yo Noun, nonindependent, auxiliary stem,*,*,*,*,yo,yo,yo
to particle, adverbialization,*,*,*,*,*,ni,ni ...
```


---
This page is auto-translated from [/nishio/mecabで入力の一部を分割しない](https://scrapbox.io/nishio/mecabで入力の一部を分割しない) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.