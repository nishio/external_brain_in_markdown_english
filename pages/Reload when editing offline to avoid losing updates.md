---
title: "Reload when editing offline to avoid losing updates"
---

from [[pRegroup2020]]
Reload when editing offline to avoid losing updates
- Show offline status/state with unsaved edits
    - Ordinary things don't need to stand out.
        - Spinner in storage
        - mark indicating a saved item is complete
    - Anything out of the ordinary should stand out.
        - off-line mode
        - Failed to save = unsaved changes are local
            - Would be nice to see unsaved changes...

- event
    - Can be edited offline (saved on the server when you come back online)
    - I'll edit things offline.
    - A bug in the drawing left me with stickies that wouldn't disappear.
    - Unintentionally reload the browser
    - Ah!
    - [Possible loss" alert if there are unsaved changes
- The latest status should be saved in localStorage in case of browser crashes, etc.
    - If I'm editing offline and trying to connect to the internet later, the power might go out.
- Next time you load, you should compare the data on the server with the local data and ask in a dialog, "The local data is newer, which one do you want to adopt?
---
This page is auto-translated from [/nishio/オフライン編集の時にリロードして更新を失わないようにする](https://scrapbox.io/nishio/オフライン編集の時にリロードして更新を失わないようにする) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.