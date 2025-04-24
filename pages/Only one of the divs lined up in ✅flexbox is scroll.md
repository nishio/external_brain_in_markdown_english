---
title: "Only one of the divs lined up in ✅flexbox is scroll"
---

When two divs are lined up on the left and right in flexbox, I want the left one to scroll because it is long vertically depending on the content in the text area, but I want the right one to ignore that scrolling because it is a menu -> Done!
![image](https://gyazo.com/760ddd3af20adee6fd532bc56601c690/thumb/1000)

I thought I could do it with maxHeight: 100%, overflowY: scroll on the left, but no luck.
- ![image](https://gyazo.com/96c3a387e2a4efdae1229f30061920a6/thumb/1000)

- Why?
- Is it because the MaterialUI dialog is changing its behavior based on the size of the contents?
    - [React Dialog component - Material-UI](https://material-ui.com/components/dialogs/)
    - I changed to a fullscreen dialog that doesn't change size, but it doesn't seem to matter because it behaves the same.
- If maxHeight: 300px, I got the expected movement.
    - But this 300px part varies depending on the environment, so I don't know what to do...

I set maxHeight: 75vh thinking that since I set it to →fullscreen dialog, I could make it viewport based.

[[Flexbox]]

Code. The width has changed from the time of the screenshot, which is not the main issue here.
    - [[Side menu with minimum width]]
ts

```typescript
<div style={{ display: "flex" }}>
  <div
    style={{ flexGrow: 1, maxHeight: "75vh", overflowY: "scroll" }}
  >
    <TextareaAutosize ... />
  </div>
  <div
    style={{
      background: "#eee",
      padding: "2px",
    }}
  >
    Menu
  </div>
</div>
```


[[pRegroup-done]]

I was given the idea of using [[position: sticky]] after making it
ts

```typescript
<div style={{ display: "flex" }}>
  <div style={{ flexGrow: 1 }}>...</div>
  <div>
    <div
      style={{
        position: "sticky",
        top: "0px",
        background: "#eee",
        padding: "2px",
      }}
    >
      Menu
    </div>
  </div>
</div>
[Sticky item needs sibling factor, is a hoax.] 
```


---
This page is auto-translated from [/nishio/✅flexboxで並べたdivの片方だけscroll](https://scrapbox.io/nishio/✅flexboxで並べたdivの片方だけscroll) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.