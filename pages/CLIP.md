---
title: "CLIP"
---

[In-depth explanation of OpenAI's new image classification model CLIP from the paper! | DeepSquare](https://deepsquare.jp/2021/01/clip-openai/)


> This is the Image & Text model CLIP, which maps text and images to a shared vector space. For applications of the models
[https://huggingface.co/sentence-transformers/clip-ViT-L-14](https://huggingface.co/sentence-transformers/clip-ViT-L-14)
[[clip-ViT-L-14]]

49408
BOS=49406
EOS=49407
python

```
>>> clip.tokenize("a painting of a cat")
tensor([[49406,   320,  3086,   539,   320,  2368, 49407,     0,     0,     0,
             0,     0,     0,     0,     0,     0,     0,     0,     0,     0,
             0,     0,     0,     0,     0,     0,     0,     0,     0,     0,
             0,     0,     0,     0,     0,     0,     0,     0,     0,     0,
             0,     0,     0,     0,     0,     0,     0,     0,     0,     0,
             0,     0,     0,     0,     0,     0,     0,     0,     0,     0,
             0,     0,     0,     0,     0,     0,     0,     0,     0,     0,
             0,     0,     0,     0,     0,     0,     0]], dtype=torch.int32)
```


subwords
python

```
>>> clip.tokenize("bozuman")
tensor([[49406,   647,  4091,   786, 49407,     0,     0,     0,     0,     0,
             0,     0,     0,     0,     0,     0,     0,     0,     0,     0,
             0,     0,     0,     0,     0,     0,     0,     0,     0,     0,
             0,     0,     0,     0,     0,     0,     0,     0,     0,     0,
             0,     0,     0,     0,     0,     0,     0,     0,     0,     0,
             0,     0,     0,     0,     0,     0,     0,     0,     0,     0,
             0,     0,     0,     0,     0,     0,     0,     0,     0,     0,
             0,     0,     0,     0,     0,     0,     0]], dtype=torch.int32)
```


---
This page is auto-translated from [/nishio/CLIP](https://scrapbox.io/nishio/CLIP) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.