---
title: "Side menu with minimum width"
---

I want to create a side menu of minimal width next to the content.

- Using [Flexbox
- If you do not specify a width for the menu, it will be just about the size of the contents.
    - By default, flex-basis: auto
- Specify flex-grow on the content side.
    - Default is 0
    - This will result in "no menu growth, only content growth.
- I didn't want the menu side to be too tight with that, so I specified padding.
- I added something like width: 20% with my old knowledge before flexbox, but it wasn't necessary.
![image](https://gyazo.com/8c5966540dd1747f2214e5982110dbec/thumb/1000)
![image](https://gyazo.com/d87b96100f2a6047f40b6ff699c58877/thumb/1000)
html

```html
<div style="display: flex">
  <div style="background: green; flex-grow: 1">
    contents
  </div>
  <div style="background: red; padding: 2px">
    menu
  </div>
</div> 
```

[CodePen](https://codepen.io/nishiohirokazu/pen/ExgLvNM)

[[pRegroup-done]]

---
This page is auto-translated from [/nishio/最小限の横幅のサイドメニュー](https://scrapbox.io/nishio/最小限の横幅のサイドメニュー) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.