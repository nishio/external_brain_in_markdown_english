---
title: "mimi"
---

Speech recognition-related services offered by Fairy Devices
Free Trial:.
- > File format that can be read is raw file. Sampling rate 16 kHz, quantization bit 16 bit, PCM, mono (1ch). Capacity is up to 5MB.
- [https://console.mimi.fd.ai/console/v1/speechrecognition](https://console.mimi.fd.ai/console/v1/speechrecognition)

- 16 kHz and 16 bits (2 bytes), so 32,000B per second, or 4,800,000B in 150 seconds
    - `$ sox in.mp3 -c 1 -r 16000 out.raw trim 0 150`
        - [[SoX]]

---
This page is auto-translated from [/nishio/mimi](https://scrapbox.io/nishio/mimi) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.