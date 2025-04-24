---
title: "Cannot write to Google Colab's local FS from TPU"
---

from  [[Japanese BERT fine-tuning]]
BERT fine-tuning ran a little and died:.

Error message: `Unsuccessful TensorSliceReader constructor: Failed to get matching files on /content/gdrive/My Drive/bert-wiki-en/model.ckpt- 1400000: Unimplemented: File system scheme '[local]' not implemented`.

Caused by not being able to write from [[TPU]] to [[Google Colab]] local FS
> Local file system is not supported on TPU. You need to use Google Storage.
[https://github.com/google-research/bert/issues/445](https://github.com/google-research/bert/issues/445)

Requires [[GCP Bucket]] as destination for exporting results

---
This page is auto-translated from [/nishio/TPUからGoogle ColabのローカルFSには書き込めない](https://scrapbox.io/nishio/TPUからGoogle ColabのローカルFSには書き込めない) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.