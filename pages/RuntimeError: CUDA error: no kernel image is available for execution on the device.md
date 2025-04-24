---
title: "RuntimeError: CUDA error: no kernel image is available for execution on the device"
---


It happened when I was trying diffuser, I checked to see if it was a different version of CUDA and it was.

python

```
>>> import torch
>>> torch.__version__
'1.12.1+cu102'
>>> torch.version.cuda
'10.2'
```


Dockerfile

```
FROM nvcr.io/nvidia/cuda:11.7.1-cudnn8-runtime-ubuntu20.04
```


![image](https://gyazo.com/e732b22fc4c5681f219de25254bde4bf/thumb/1000)
[https://pytorch.org/get-started/locally/](https://pytorch.org/get-started/locally/)
`$ pip install --upgrade torch torchvision torchaudio --extra-index-url https://download.pytorch.org/whl/cu113`

python

```
>>> torch.version.cuda
'11.3'
```


---
This page is auto-translated from [/nishio/RuntimeError: CUDA error: no kernel image is available for execution on the device](https://scrapbox.io/nishio/RuntimeError: CUDA error: no kernel image is available for execution on the device) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.