---
title: "_pickle.UnpicklingError: invalid load key, 'v'"
---

> If git lfs is not included, the clone of the pre-trained model will get pointer information instead of entities, so when I run the code, I get something like _pickle.UnpicklingError: invalid load key, 'v'. I was hooked for a while when I ran the code.
[https://zenn.dev/ryoma310/articles/63bc3d20a8746c](https://zenn.dev/ryoma310/articles/63bc3d20a8746c)

In the [[Textual Inversion]] environment build, I copied and placed a model file with 4 gigs of [[Stable Diffusion]], but it probably references another model from within this model, which I cannot find, causing this error.

`$ apt-get install git-lfs`
`$ git lfs install`
`$ git lfs pull`

---
This page is auto-translated from [/nishio/_pickle.UnpicklingError: invalid load key, 'v'](https://scrapbox.io/nishio/_pickle.UnpicklingError: invalid load key, 'v') using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.