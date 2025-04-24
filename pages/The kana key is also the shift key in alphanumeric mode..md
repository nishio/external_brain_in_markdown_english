---
title: "The kana key is also the shift key in alphanumeric mode."
---

json

```json
{
  "description": "Change lang1(Kana) to left_shift. (Post lang1 if pressed alone)",
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
        "key_code": "lang1",
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
          "key_code": "lang1"
        }
      ],
      "type": "basic"
    }
  ]
}
```



---
This page is auto-translated from [/nishio/かなキーを英数モードではシフトキーにもする](https://scrapbox.io/nishio/かなキーを英数モードではシフトキーにもする) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.