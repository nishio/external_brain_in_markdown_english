---
title: "mask again after inpaint"
---

py

```
import numpy as np
from PIL import Image

init_image = Image.open("init_image.png")
mask_image = Image.open("mask_image.png")
cat_image = Image.open("cat_on_bench.png")

m = np.array(mask_image) / 255.0
bg = np.array(init_image) * (1 - m)
fg = np.array(cat_image) * m
img = bg + fg
img = img.astype(np.uint8)
Image.fromarray(img, "RGB").save("out.png")
```


![image](https://gyazo.com/1a38c6deac8fb1c7e78035413fa868a9/thumb/1000)

---
This page is auto-translated from [/nishio/mask again after inpaint](https://scrapbox.io/nishio/mask again after inpaint) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.