---
title: "The input field and most recent statement overlap with the keyboard."
---

In chat apps where the input field and most recent statement are at the bottom of the screen, the iOS virtual keyboard was causing an inconvenience.

solution
- The basic policy is window.scrollTo
- Network response increases logging.
    - Content updates asynchronously and changes height at unpredictable times
    - React.useEffect is called after rendering the component, use this
        - `const [logs, setLogs] = useState(...)`
        - SetLogs in response to trigger redrawing
    - `useEffect(scrollToBottom, [logs])` to scroll after rendering
    - Now this pathway is resolved.
- Text area changes size depending on the amount of text inside.
    - [[TextareaAutosize]] in [[Material-UI]]
    - Scrolling with onChange didn't work.
        - Because the rendering is not yet finished at this time.
        - [TextareaAutosize](https://github.com/mui-org/material-ui/blob/next/packages/material-ui/src/TextareaAutosize/TextareaAutosize.js)
            - Check the height when changing content and setState if it needs to be updated.
            - The rendering of the component runs when this change is triggered.
        - I couldn't figure out how to do hooks after rendering child components.
            - `setTimeout(scrollToBottom);` do
            - There may be no guarantee that this will be after the rendering.
- Contents of scrollToBottom
ts

```typescript
const scrollToBottom = () => {
  const e = document.getElementById("bottom") as HTMLElement;
  const y = e.offsetTop - document.documentElement.clientHeight + 300;
  if (y > 0) {
    window.scrollTo(0, y);
  }
};
```

    - 300 is the height of the virtual keyboard. Could not figure out how to get it from the device.
        - According to the reference material (*1), it was 301, and the experiment with 11ProMax at hand seemed to be OK, so this is what we did.
    - BOTTOM has hr under the input field.
- [diff](https://github.com/nishio/keicho-webclient/commit/33160de16bfd2feb4da08fb47e91b6f16f7cde3a)

- Related [[Focus is lost after text entry]].
reference data

[https://github.com/mui-org/material-ui/blob/next/packages/material-ui/src/TextareaAutosize/TextareaAutosize.js](https://github.com/mui-org/material-ui/blob/next/packages/material-ui/src/TextareaAutosize/TextareaAutosize.js)
[[pKeicho]]

> When retrieving with window.innerHeight, the value that can be obtained is different when the address bar is displayed by scrolling up and when the address bar is not displayed by scrolling down.
>  When retrieving with document.documentElement.clientHeight, there is no effect by the address bar and a constant value can always be obtained.
- [Get screen size in Safari on iOS | chocolateorange.github.io](https://chocolateorange.github.io/2016/09/23/01/)

- [ios - What is the height of iPhone's onscreen keyboard? - Stack Overflow](https://stackoverflow.com/questions/11284321/what-is-the-height-of-iphones-onscreen-keyboard)
    - (*1)[List of the official iOS keyboards’ heights (and how to calculate them) | by Federica Benacquista | Dec, 2020 | Medium](https://federicabenacquista.medium.com/list-of-the-official-ios-keyboards-heights-and-how-to-calculate-them-c2b844ef54b9)
[The Eccentric Ways of iOS Safari with the Keyboard | by David Fedor | Open Digerati](https://blog.opendigerati.com/the-eccentric-ways-of-ios-safari-with-the-keyboard-b5aa3f34228d)
[html - Iphone safari not resizing viewport on keyboard open - Stack Overflow](https://stackoverflow.com/questions/39417778/iphone-safari-not-resizing-viewport-on-keyboard-open)
[iphone - iPad Web App: Detect Virtual Keyboard Using JavaScript in Safari? - Stack Overflow](https://stackoverflow.com/questions/2593139/ipad-web-app-detect-virtual-keyboard-using-javascript-in-safari)
[Issues with position fixed & scrolling on iOS](https://remysharp.com/2012/05/24/issues-with-position-fixed-scrolling-on-ios)

[[virtual keyboard]]

---
This page is auto-translated from [/nishio/入力欄と直近発言がキーボードとかぶる](https://scrapbox.io/nishio/入力欄と直近発言がキーボードとかぶる) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.