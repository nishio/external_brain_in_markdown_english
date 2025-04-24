---
title: "Toggle Firestore connection or not depending on URL parameter"
---

from [[pRegroup-done-2019]]
Toggle Firestore connection or not depending on URL parameter

done
- Mock for implementation testing (no connection) if /dev
    - Toggle the display of the UI under development according to the flag of whether it is a development screen or not
- If it's /manual, it's a function explanation screen assuming I'm not around.
    - Like /edit_manual to edit the manual to create this.
        - Only I need to be able to edit it.
- If /blank, then blank screen that is not saved for use testing or demonstration
- Preset for demo if it is /demo

- Automated testing if /test
- If /foo, load foo from Firestore

How do you do nothing? →Pending.

- Screen for manual display
- Screen for manual editing
- Changes to the screen for editing are saved in Firestore.
- The screen for display can be changed, but not saved.

---
This page is auto-translated from [/nishio/URLパラメータによってFirestore接続の有無を切り替え](https://scrapbox.io/nishio/URLパラメータによってFirestore接続の有無を切り替え) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.