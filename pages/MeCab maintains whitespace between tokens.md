---
title: "MeCab maintains whitespace between tokens"
---

I want it to revert back to what it was when I rejoin what I chopped into tokens.
python

```
>>> concat_tokens(tokenize("This is a pen"))
'This is a pen'
```

But MeCab's node.surface doesn't contain spaces, so the common way would be 'Thisisapen'.
This problem was solved.

Since there is `%M morpheme surface string, but including whitespace` in [MeCab: output format](https://taku910.github.io/mecab/format.html), I thought the parsed node should have the necessary information to display this
- [code](https://github.com/taku910/mecab/blob/3a07c4eefaffb4e7a0690a7f4e5e0263d3ddb8a3/mecab/src/writer.cpp#L280)
cpp

```cpp
case 'S': os->write(reinterpret_cast<const char*>
                    (node->surface -
                     node->rlength + node->length),
                    node->rlength - node->length);
```

- So instead of having the whitespace itself in front, node.rlength has a length that includes whitespace
- Without seeing the original string, it's impossible to know what characters actually preceded the token and were ignored.

python

```
word = node.surface
# keep whitespace before token
wslength = node.rlength - node.length
ws = s[start:start+wslength]
word = ws + word
```


---
This page is auto-translated from [/nishio/MeCabでトークン間の空白を維持](https://scrapbox.io/nishio/MeCabでトークン間の空白を維持) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.