---
title: "Books have a special language model for table of contents and index"
---

Problems with using books as a corpus

The books are
- preface
- Table of Contents
- body (of letter)
- index
structure, but the language model of the table of contents and index is clearly unique
If you simply split the data 80%-10%, the data for testing will be indexed in its entirety, and it will never work.
For now, visually designate the beginning and end of the text.
python

```
In [44]: re.findall("In the beginning", data)
Out[44]: ['In the Introduction'].

In [45]: re.findall("Looking forward to it." , data)
Out[45]: ['Looking forward to it.']
```


python

```
BEGIN_BODY = "In the Introduction"
END_BODY = "Looking forward to it."
assert len(re.findall(BEGIN_BODY, data)) == 1
assert len(re.findall(END_BODY, data)) == 1
data = data[data.index(BEGIN_BODY) : data.index(END_BODY) + len(END_BODY)] 
```


However, since Chapter 1 and Chapter 7 deal with different topics, the words that appear in them are also different, so simply dividing the text into 80% and 10% after extracting the text is no good, right? I have a feeling that this is not a good idea.
Maybe we should split it up into separate pages and then divide it up - I don't know.

#natural language processing #book corpus

---
This page is auto-translated from [/nishio/書籍は目次と索引の言語モデルが特殊](https://scrapbox.io/nishio/書籍は目次と索引の言語モデルが特殊) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.