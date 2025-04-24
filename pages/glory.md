---
title: "glory"
---

2020-04-07
![image](https://gyazo.com/f93f2cef2da0f4501a5b8448ee3199d6/thumb/1000)

python

```
from skimage import filters
from skimage import io
import numpy as np

WIDTH = 480
HEIGHT = 360
T = 20
data = np.zeros((HEIGHT, WIDTH, 3))

N = 75
data[HEIGHT // 2, WIDTH // 2] = (0, N * N, 0)
data = filters.gaussian(data, sigma=N, multichannel=True)
data /= data.max()
data *= 255
data *= T
data = data.astype(np.uint8)
io.imsave("tmp.png", data)
```


T=20
![image](https://gyazo.com/ef46c14469f56ed07bbb39bfc0135efb/thumb/1000)
T=60
![image](https://gyazo.com/9dfb795efb294d42fabaf9346b2afbf6/thumb/1000)
T=100
![image](https://gyazo.com/a8f427b963e8670375b41a0eda06da0c/thumb/1000)

T=200
![image](https://gyazo.com/be447a8838e9c86cc8f57bdd2d32c922/thumb/1000)

T=400
![image](https://gyazo.com/bb9b1d48870821b8ae739bff2ff2ea0b/thumb/1000)

T=600
![image](https://gyazo.com/fc32eeb3167631c8ef96f142ecb479f3/thumb/1000)

Movie
[https://youtu.be/AuiNWkJlk-w](https://youtu.be/AuiNWkJlk-w)

YouTube's codecs effect
- original
    - ![image](https://gyazo.com/51f81bc42e3f9d8b671bae00a4bcbfc7/thumb/1000)
- on YouTube
    - ![image](https://gyazo.com/9c04582938f2a984548a92bbdd79ec2a/thumb/1000)

---
This page is auto-translated from [/nishio/後光](https://scrapbox.io/nishio/後光) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.