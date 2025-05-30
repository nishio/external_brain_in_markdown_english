---
title: "Thumb Shift with Ergodox"
---

![image](https://gyazo.com/25bb95bcf21ce686ff90fc7ccf238e48/thumb/1000)

Ergodox enabled thumb shift.
- It is common to use key rewriting software such as DvorakJ for thumb shift in a Windows environment.
- However, DvorakJ
    - The design considers keys to be struck at the same time if the time difference between them is within a certain range, so a slight delay in keystrokes is judged as not being simultaneous.
    - Extensive damage when space, conversion, no conversion, etc. are used as shift keys by default and determined not to be simultaneous.
    - Perhaps this design causes `git add -p` to become `gi tad d-p` or `"abc"` to become `"abC'`.
        - A space or shift is pressed after the alphabet, but the alphabet is recognized late.
- Therefore, we realized thumb shift using Ergodox EZ, a firmware rewritable keyboard.
- I did what I wanted to do because I didn't have the motivation to reproduce the placement of the symbols as per the specifications.
- Surprisingly, there are no articles about it, so I'm writing about it here.

Technical
- I put the source here.
    - [https://github.com/nishio/qmk_firmware/tree/thumb_shift/keyboards/ergodox/keymaps/thumb_shift](https://github.com/nishio/qmk_firmware/tree/thumb_shift/keyboards/ergodox/keymaps/thumb_shift)
- Shift key-like behavior is implemented directly in macros, rather than using existing key codes as thumb shift keys.
    - So there is no harm in striking empty.
    - With two more modifier keys
- Most of the key definitions are macros [https://github.com/nishio/qmk_firmware/blob/thumb_shift/keyboards/ergodox/keymaps/thumb_shift/keymap.c#L22](https://github.com/nishio/qmk_firmware/blob/thumb_shift/keyboards/ergodox/keymaps/thumb_shift/keymap.c#L22)
- A related article that is not thumb shift but is helpful [Implementing simultaneous thumb strike with Ergodox](https://qiita.com/derui@github/items/060eebf33716d703b90c)
    - I was worried about the size being severe, but it worked easily and without any problems.
    - [his implementation](https://github.com/derui/qmk_firmware/blob/master/layouts/community/ergodox/derui/hk_util.c#L64) and [my implementation [https://github.com/](https://github.com/) nishio/qmk_firmware/blob/thumb_shift/keyboards/ergodox/keymaps/thumb_shift/keymap.c#L81] may differ in size by one digit
- Key code sequences that cannot be simply expressed are treated as special commands when the first character KC_NO is followed by a non-zero value.
    - [https://github.com/nishio/qmk_firmware/blob/thumb_shift/keyboards/ergodox/keymaps/thumb_shift/keymap.c#L144](https://github.com/nishio/qmk_firmware/blob/thumb_shift/keyboards/ergodox/keymaps/thumb_shift/keymap.c#L144)
- English letters and symbols not yet implemented.
- It would be nice to modify the arrow keys with thumb shift to Home and PageUp.
---
This page is auto-translated from [/nishio/Ergodoxで親指シフト](https://scrapbox.io/nishio/Ergodoxで親指シフト) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.