---
title: "Talk to the City's environment in Python 3.11"
---


[[Talk to the City]]

The README contains
> We recommend to use python 3.10+ and install the dependencies as follows:
but it won't work as it is because distutils will be lost in Python 3.11.

`$ pip install --upgrade pip setuptools`
as a result of

I modified some of the requirements.txt and it worked.
:

```
numpy>=1.25.2
tiktoken>=0.5.1
```


---
This page is auto-translated from [/nishio/Talk to the CityのPython3.11での環境構築](https://scrapbox.io/nishio/Talk to the CityのPython3.11での環境構築) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.