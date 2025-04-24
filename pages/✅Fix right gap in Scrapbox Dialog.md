---
title: "✅Fix right gap in Scrapbox Dialog"
---

from  [[Improve the appearance of the ✅ dialog]]
Fix right gap in Scrapbox Dialog

after:
- ![image](https://gyazo.com/36c9901f53277a1f2fabebe03d133b52/thumb/1000)

before:
- ![image](https://gyazo.com/c521e80e41d01b51bdb5a7c4def5a3b2/thumb/1000)

movie:
- ![image](https://gyazo.com/24c0120e89e939636c820c8a9b2fd128/thumb/1000)

- Before, we had to name the content in the items of flex by class name and apply CSS to control the size.
    - In the after, the class name is added to the items themselves.
    - Instead of setting a fixed size with width, let it be adjusted with flex.
- The div that wraps the button is fixed to the size of its content with `flex-basis: auto;`.
- The div in the input field is filled with a fixed value of basis, and then grow is used to fill the available space.
    - The input field inside matches the size of the div outside.
css

```
div.input-icon {
  flex-basis: 120px;
  flex-grow: 1;
}
div.input-icon > div {
  width: 100%;
}
```

- The page title needs to be longer if possible, and the project name does not need to be much longer, this is expressed by the different values of grow
    - There may be a better way to go about this.

[[Flexbox]]

---
This page is auto-translated from [/nishio/✅Scrapbox Dialogの右の隙間を修正](https://scrapbox.io/nishio/✅Scrapbox Dialogの右の隙間を修正) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.