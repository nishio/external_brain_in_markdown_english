---
title: "WheatSeedsSystem Development Diary 2021-11-18"
---

[[pWheatSeedsSystem]]
- [[Mechanism for combining multiple resource packs]]
![image](https://gyazo.com/5a4c77e9fc384b151da1140a3c0d5483/thumb/1000)
- Originally used as a server resource pack at [[CybozuHackathon2021]] so everything was in one resource pack (1)
- When releasing a resource pack after a hackathon, it's hard to give it a title or anything like that, "Here's a resource pack with a lot of stuff in it.
    - The title "the one I made at the Cybozu Hackathon" is too subtle.
    - Therefore, it was divided and released by theme (2)
- However, with this design, the seeded part is the same object, so if multiple resource packs are installed, the later one will overwrite the earlier one and stop working.
    - So put references to all objects in the seed of all packs (3)
- This still didn't work, so I was afraid it could only refer to objects in the same pack.
    - I made the all-inclusive pack I originally planned to make, but the problem reproduced itself, so it wasn't caused by the inability to reference across packs.
    - Cause.
        - [https://github.com/nishio/wheat_seeds_system/commit/98b1dca242f0ede0129a0e6001811dff1a5b0279](https://github.com/nishio/wheat_seeds_system/commit/98b1dca242f0ede0129a0e6001811dff1a5b0279)

Released.
> I released v0.5.0 and now you can use this pack with other wheat system packs!

Level 10.

---
This page is auto-translated from [/nishio/WheatSeedsSystem開発日記2021-11-18](https://scrapbox.io/nishio/WheatSeedsSystem開発日記2021-11-18) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.