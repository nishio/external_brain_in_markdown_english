---
title: "Split audio files"
---

:

```
ffmpeg -i input.mp3 \
 -f segment \ # segment mode
 -segment_time 1800 \ # every 1800 seconds
 -c copy \ # Do not recompress encoding (fast, no degradation)
 output_%03d.mp3          # output_000.mp3, output_001.mp3, ...
```


ffmpeg -i ~/Downloads/05-10_xxx.mp3 -f segment -segment_time 9000 -c copy output_%03d.mp3


---
This page is auto-translated from [/nishio/音声ファイルを分割](https://scrapbox.io/nishio/音声ファイルを分割) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.