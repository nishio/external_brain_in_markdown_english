---
title: "Kozaneba Development Diary 2021-12-10"
---

prev  [[Kozaneba Development Diary 2021-11-26]]

- [[Why are lines essential?]]

Kozaneba, when you select a range and drag or delete it, it mysteriously takes longer?
Something's wrong.
Even if the number of sticky notes increased by a factor of five, a factor of five wouldn't slow things down this much.
I'll be sad if I do some weird experiment and corrupt the data, so let's wait until after the presentation.

Bug: When a duplicate is created, "copy" is attached to one of the copies at the time of creation, but it disappears at some point in time.

Hey, this is the release version of Kozaneba, I think you didn't deploy the line edge shifting bug that you fixed before.

Should the loading display appear immediately upon pasting an image URL?
I'd rather have a normal kozane once when re-importing from Scrapbox, and then copy and paste it back in individually, but I don't know if that's possible to do in the menu.

Ah, I see, I'm starting to get it.
When I move the kozane, the more of them there are, the slower they follow the mouse movement.
If the event hits img at that time, will that one be dragged?

2021-12-18
- [[Kozaneba: The Formation of Chinese Hua Yan through the Fusion of the Hua Yan Sutra and Zhuangzi]]
Lines drawn on top make what is below unreadable.
- ![image](https://gyazo.com/03016108aef6132b82798cacefa8f0c6/thumb/1000)
- You can't put it down (because it can lead to a kozane in the group).
- It's not good to have to move it to read it.
- Make it translucent?
    - I stopped making it semi-transparent once because the arrows weren't a good representation.
        - [[Kozaneba Development Diary 2021-09-09#6139aed3aff09e000025bf90]]
        - Maybe just the line part could be translucent.

[[pKozaneba]]

---
This page is auto-translated from [/nishio/Kozaneba開発日記2021-12-10](https://scrapbox.io/nishio/Kozaneba開発日記2021-12-10) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.