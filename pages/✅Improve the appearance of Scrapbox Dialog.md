---
title: "✅Improve the appearance of Scrapbox Dialog"
---

from  [[Improve the appearance of the ✅ dialog]]
Improve the appearance of Scrapbox Dialog
after:
![image](https://gyazo.com/84ce13f8e1e4073f3fdffc0da100172c/thumb/1000)

- before
    - ![image](https://gyazo.com/d01f8b60f3dfe9ca5ba2f5154044085c/thumb/1000)
- In the meantime, I'd like to do something about the bumps up and down.
    - The input fields are directly in the input tag, and the buttons are in the Material-UI, so it would be good to align them with the latter.
        - Input field [Text Field React component - Material-UI](https://material-ui.com/components/text-fields/)
- Add background color to buttons
    - variant="contained" [React Button component - Material-UI](https://material-ui.com/components/buttons/)
    - ![image](https://gyazo.com/0eb4f93d2ac3c77ff0ed64b878506122/thumb/1000)
- I don't need so much padding in the input field.
css

```
.MuiOutlinedInput-input {
    padding: 9px;
}
```

    - ![image](https://gyazo.com/f9a6013f0b6ea724acb2d47ef91b18be/thumb/1000)
- I want to fix the label sticking out due to lack of margin.
css

```
.dialog-inputs > div {
  margin-top: 7px;
}
```

    - ![image](https://gyazo.com/7856c9b750e100efade7fb5c1e37c0e3/thumb/1000)

- What would happen with iPhone X size
    - ![image](https://gyazo.com/94bc7583e7c90ae292743e5e80c3dbdb/thumb/1000)
- Try adjusting the size
    - ![image](https://gyazo.com/84ce13f8e1e4073f3fdffc0da100172c/thumb/1000)
        - Hmmm, personally I'd like to see this place aligned...
        - ![image](https://gyazo.com/c521e80e41d01b51bdb5a7c4def5a3b2/thumb/1000)
- Improvements.
        - [[✅Fix right gap in Scrapbox Dialog]]

---
This page is auto-translated from [/nishio/✅Scrapbox Dialogの見た目を改善する](https://scrapbox.io/nishio/✅Scrapbox Dialogの見た目を改善する) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.