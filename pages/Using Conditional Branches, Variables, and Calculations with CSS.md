---
title: "Using Conditional Branches, Variables, and Calculations with CSS"
---

    - [[media query]] allows conditional branching
    - [Using Media Queries - CSS: Cascading Style Sheets | MDN](https://developer.mozilla.org/ja/docs/Web/CSS/Media_Queries/Using_media_queries)
    - I was under the impression that it was something that switched between the print screen and the normal screen (it's called "media").
    - But screen size can be added to the conditional expression
    - You can create variables with [[custom property]].
    - [Using CSS custom properties (variables) - CSS: Cascading Style Sheets | MDN](https://developer.mozilla.org/ja/docs/Web/CSS/Using_CSS_custom_properties)
    - The :root pseudo-class can be used in place of the global scope.
- It can be calculated with calc().
    - [calc() - CSS: Cascading Style Sheets | MDN](https://developer.mozilla.org/ja/docs/Web/CSS/calc)
- Can be retrieved by JS.
    - `getComputedStyle(document.body).getPropertyValue("--toolbar-height")`
    - Since it's a string, if we assume units, it looks like this
ts

```typescript
const toolbarHeight = parseInt(
    getComputedStyle(document.body)
      .getPropertyValue("--toolbar-height")
      .trim()
  );
```


css to shrink the height of the toolbar and buttons when the width is narrow
css

```
:root {
  --toolbar-height: 60px;
}
@media only screen and (max-width: 600px) {
  :root {
    --toolbar-height: 36px;
  }
}

#toolbar {
  height: var(--toolbar-height);
}
#toolbar svg {
  height: calc(var(--toolbar-height) * 0.8);
  margin: calc(var(--toolbar-height) * 0.1) 0 calc(var(--toolbar-height) * 0.1) 0;
}
```

These days [[CSS]] is useful!

css

```
/* Spacers to divide 7 buttons into 3 groups */
#toolbar span.spacer {
  margin-left: calc((100vw - var(--button-size) * 7) / 2);
}
```


digression
- Can also pattern-match to class names.
    - [Attribute selectors - CSS: Cascading Style Sheets | MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/Attribute_selectors?fbclid=IwAR0QOFAM0qUYu8eWeDTveDUrH3fbEhYRh3ocF-6M-z61wrfdELQitgcOdfs)

---
This page is auto-translated from [/nishio/CSSで条件分岐と変数と計算を使う](https://scrapbox.io/nishio/CSSで条件分岐と変数と計算を使う) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.