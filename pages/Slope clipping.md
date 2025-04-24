---
title: "Slope clipping"
---

python

```
optimizer.add_hook(chainer.optimizer_hooks.GradientClipping(args.gradclip))
```

[https://docs.chainer.org/en/stable/examples/ptb.html](https://docs.chainer.org/en/stable/examples/ptb.html)

- Easy to [[clipping]] so that [[gradient]] does not exceed the threshold #Chainer

---
This page is auto-translated from [/nishio/勾配クリッピング](https://scrapbox.io/nishio/勾配クリッピング) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.