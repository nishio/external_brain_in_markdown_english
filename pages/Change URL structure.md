---
title: "Change URL structure"
---

Change URL structure
- I had forgotten all about it because I was the only one who used it before, but before other users used it.
    - It needs to be changed to `#/<user>/<mapName>/<options>` or something like that.
- Actually, while I was using it on my own, the system granted editing privileges when the map name ends in EDIT.
    - `#/<mapName>edit`
    - This implementation needs to stop before sharing editable links to others.
- I had the above thoughts as of July, but changed my mind when I looked back in December.
    - `#/key=<key>`
        - Unless you need to put the hierarchical structure in the URL, avoid it.
        - I don't need to put the user in the URL, same idea as [[Gyazo]].
        - Not "easy-to-understand URLs," but since it's unclear that easy-to-understand is really necessary, simplicity is the priority.
        - Actually, you don't even need `key=`, but it's a combination of existing URLs.
    - Readonly and other settings can be made on the object pointed to by key.
        - For example, if you have given an edit permission link to an inappropriate person, you can remove the key from the DB.
        - In the future, it would be nice to have something like [putting a moratorium on changes
    - demerit
            - [[Listing of maps created by you]] is difficult to do.
            - I'll think about this when I need it.

relevance
    - [[access right]]
[[pRegroup-done-2019]]

---
This page is auto-translated from [/nishio/URLの構造を変更](https://scrapbox.io/nishio/URLの構造を変更) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.