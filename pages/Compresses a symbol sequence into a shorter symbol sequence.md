---
title: "Compresses a symbol sequence into a shorter symbol sequence"
---

- [[symbol string]] Compress X into a shorter symbol string Y
![image](https://gyazo.com/2d52857e9fa35f358ad9ee550b247390/thumb/1000)
I thought that the first thing I needed was a device that could produce an output of indefinite length from symbol sequence Y back to symbol sequence X.
In the figure, it looks like an RNN, but the current major implementation is a "dictionary object that produces a string of indefinite length when a word ID is entered.
![image](https://gyazo.com/2048c3993943878690e2f36e76e0ed1c/thumb/1000)

One more point: If we produce a sequence of symbols like this, and then think about what happens to them, we embed the symbols in a vector, right? So, in the final stage of this device, symbols are created from the embedded representation, so wouldn't it be better to transmit the symbols as they are without changing them into symbols? Isn't "outputting as a symbol" necessary just to put it into a form that humans can understand? I thought so. [Human IO is hefty.
![image](https://gyazo.com/b05ac038bb05df43f1cb30bbe678d203/thumb/1000)


---
This page is auto-translated from [/nishio/シンボル列をより短いシンボル列に圧縮する](https://scrapbox.io/nishio/シンボル列をより短いシンボル列に圧縮する) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.