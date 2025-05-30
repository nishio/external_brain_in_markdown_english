---
title: "Focus is lost after text entry"
---

- Focus is lost after text entry
    - It didn't come off before.
- Recent updates include "Hide input fields when errors occur"
    - In hiding the input field when an error occurs, I put all the HTMLTextareaElement and buttons together into a function component.
    - This implementation is one that internally looks at props.visible and branches
ts

```typescript
const InputArea = (props: { visible: Boolean }) => {
  if (props.visible) {
    return ...;
  }
  return null;
};
```

    - My interpretation: this means that while visible is true, the component re-rendering does not run because the props are shallowly identical.
        - However, behavior such as losing focus suggests that the HTMLTextareaElement has disappeared and is being regenerated.
- The out-of-focus itself could be solved by adding the autoFocus attribute.
    - Scroll now misaligned.
    - The large discrepancy was resolved by requestingAnimationFrame to scroll after the rendering of that input field component was finished.
    - but a subtle (8px) discrepancy remained.
        - If it doesn't move, I don't care if it's out of alignment, but it's depressing because it animates up and down 8 pixels with each input.
- Determined that the regenerated DOM is complicating matters
    - The text area is now outside of the if statement and controlled by visibility of style.
    - Now there is no displacement without requestAnimationFrame.
    - However, there will be an 8px discrepancy once you leave the browser and return to it.
        - The virtual keyboard is turned on and off in the process, so I'm guessing that this may have something to do with it.
- This is hr margin-bottom.
    - Resolved with margin-bottom: 0; border-bottom: 0;.
    - So only when the "content is shorter than the current display area" due to the disappearance of the virtual keyboard or, if placed before modification, the input field component, the scrolling will be too far ahead by that margin.

[[pKeicho-done]]

---
This page is auto-translated from [/nishio/テキスト入力後にフォーカスが外れる](https://scrapbox.io/nishio/テキスト入力後にフォーカスが外れる) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.