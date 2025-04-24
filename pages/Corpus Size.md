---
title: "Corpus Size"
---

python

```
train, val, test = chainer.datasets.get_ptb_words()
len(train), len(val), len(test)
# (929589, 73760, 82430)
```

1085779 in total. 10000 different numbers.

Engineers' Intellectual Productivity is 168489 in words and 292661 in letters.
Number of different words 7406 Number of different letters 1581
When I looked at the most common word frequencies, there were too many periods, which I attributed to the dotted lines in the table of contents index, etc.
`data = re.sub(r"\.\.\.\.+", "DOTTEDLINE", data)`
232870 123718 1581 7411


---
This page is auto-translated from [/nishio/コーパスのサイズ](https://scrapbox.io/nishio/コーパスのサイズ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.