---
title: "Reset VRAM on Google Colab"
---

I was doing a process in Google Colab that used a lot of video memory, and the first time it worked, but the second time I got an error because I didn't have enough memory.
This is due to the fact that "instances that are not needed are still alive grabbing video memory.
- The first run, Y was not yet created when doing X. The second run, X is done with the remaining Y created in the first run.
- Colab's environment keeps grabbing global variables created in the past, which is why they are not GC'd.

So we explicitly release it.
py

```
from numba import cuda
device = cuda.get_current_device() 
device.reset()
```

[google colaboratory - Can i clear up gpu vram in colab - Stack Overflow](https://stackoverflow.com/questions/71371756/can-i-clear-up-gpu-vram-in-colab)

Not tested if this is correct.

---
This page is auto-translated from [/nishio/Reset VRAM on Google Colab](https://scrapbox.io/nishio/Reset VRAM on Google Colab) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.