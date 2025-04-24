---
title: "Connecting videos with ffmpeg"
---

OsmoAction will split every 4 gigs when taking long videos with OsmoAction.
It's too much trouble to use Premiere just to connect this, so I'll do it with [[ffmpeg]].

Prepare a file with the name of the target file on each line with `file ` at the beginning of the line.
`$ ls DJI_0577* | sed -e 's/^/file /' > t.txt`

Combine.
`$ ffmpeg -f concat -i t.txt -c copy output.mp4`
Output: `frame=184209 fps=491 q=-1.0 Lsize=75104689kB time=01:42:26.40 bitrate=100100.4kbits/s speed=16.4x`

But, well, it's simply a combination of the two, so you get a 77 gig file.
`-rwxr-xr-x 1 nishio nishio 76907201729 Jan 20 15:13 output.mp4`

[Encode/YouTube – FFmpeg](https://trac.ffmpeg.org/wiki/Encode/YouTube)
`$ ffmpeg -i input.avi -c:v libx264 -preset slow -crf 18 -c:a copy -pix_fmt yuv420p output.mkv`
What is [[.mkv]] [Matroska - Wikipedia](https://ja.wikipedia.org/wiki/Matroska)

`-rwxr-xr-x 1 nishio nishio 2573372618 Jan 20 19:07 output.mkv`
`-rwxr-xr-x 1 nishio nishio 76907201729 Jan 20 15:13 output.mp4`

I can't open mkv in Premiere...
I'll upload it to YouTube as is.
![image](https://gyazo.com/8a08d3b1e302acb16e0476957c1d3b80/thumb/1000)
6:44???


---
This page is auto-translated from [/nishio/ffmpegで動画をつなぐ](https://scrapbox.io/nishio/ffmpegで動画をつなぐ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.