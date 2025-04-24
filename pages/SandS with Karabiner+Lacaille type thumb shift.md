---
title: "SandS with Karabiner+Lacaille type thumb shift"
---

When I write a program after changing Japanese input to thumb shift, I want the SandS (space long press and shift key) function.
- [[Thumb Shift Diary on Mac 2020-01#5e02ec55aff09e0000449fba]]
    - Or rather, my right thumb is on standby on the conversion key, but I don't need it at all when writing programs, so why not if this is the shift for English letters...?
    - Done [[The kana key is also the shift key in alphanumeric mode.]]
    - We won't talk about this at this time.

- SandS for [karabiner-element
    - [https://pqrs.org/osx/karabiner/complex_modifications/#spacebar](https://pqrs.org/osx/karabiner/complex_modifications/#spacebar)
    - You can't do things like alphanumeric mode only, so it clashes with the space key being used as a left shift for thumb shift.
        - Because Lacaille distinguishes between left thumb shift and pinky shift.
    - Then just limit it to alphanumeric mode.
        - I solved the problem by editing ~/.config/karabiner/karabiner.json directly.

condition entry
json

```json
"conditions": [
  {
    "input_sources": [
      {
        "input_mode_id": "com.apple.inputmethod.Roman"
      }
    ],
    "type": "input_source_if"
  }
],
```


whole
json

```json
{
  "description": "Change spacebar to left_shift. (Post spacebar if pressed alone)",
  "manipulators": [
    {
      "conditions": [
        {
          "input_sources": [
            {
              "input_mode_id": "com.apple.inputmethod.Roman"
            }
          ],
          "type": "input_source_if"
        }
      ],
      "from": {
        "key_code": "spacebar",
        "modifiers": {
          "optional": [
            "any"
          ]
        }
      },
      "to": [
        {
          "key_code": "left_shift"
        }
      ],
      "to_if_alone": [
        {
          "key_code": "spacebar"
        }
      ],
      "type": "basic"
    }
```



---
This page is auto-translated from [/nishio/Karabiner+Lacaille型親指シフトでSandS](https://scrapbox.io/nishio/Karabiner+Lacaille型親指シフトでSandS) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.