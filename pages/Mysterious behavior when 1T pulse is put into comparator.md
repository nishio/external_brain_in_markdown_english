---
title: "Mysterious behavior when 1T pulse is put into comparator"
---

If the micra comparator is looped, the signal strength is maintained with a 1-tick delay in the comparator portion, and the signal strength drops by 1 with no delay in the powder portion. However, if you put a 1-tick pulse in this, it will decay and disappear in the continuous part of the comparator.
It does not occur at more than 2 ticks.
Verified by JE1.17.1.

If you put a 1-tick signal in the observer, it stops in the middle of the signal.
[https://scrapbox.io/files/61487b12de6c1c0022ce4c2f.mp4](https://scrapbox.io/files/61487b12de6c1c0022ce4c2f.mp4)
If it's more than two ticks, it's seven and a half laps.
[https://scrapbox.io/files/6148803eb035cb001d14f8f1.mp4](https://scrapbox.io/files/6148803eb035cb001d14f8f1.mp4)

[Redstone Comparator - Minecraft Wiki](https://minecraft.fandom.com/ja/wiki/レッドストーンコンパレーター)
- states the following, which is not true
- > Redstone comparators typically do not respond to changes in signal strength of one tick.

---
This page is auto-translated from [/nishio/コンパレータに1Tのパルスを入れると不思議な挙動](https://scrapbox.io/nishio/コンパレータに1Tのパルスを入れると不思議な挙動) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.