---
title: "Over 200 classes were generated"
---

:

```
Over 200 classes were generated for component styled.div with the id of "sc-jrsJWt".
Consider using the attrs method, together with a style object for frequently changed styles.
Example:
  const Component = styled.div.attrs(props => ({
    style: {
      background: props.background,
    },
  }))`width: 100%;`
```


I was not familiar with [[styled-components]] and wrote something like this, but this is not appropriate because it will create different classes for different props
ts

```typescript
export const KozaneDiv = styled.div`
  ...
  top: ${(props) => props.style?.top ?? "0px"};
  left: ${(props) => props.style?.left ?? "0px"};
```


You don't have to bother writing this, since the style is the final DOM Element style, so you can simply delete it.
---
This page is auto-translated from [/nishio/Over 200 classes were generated](https://scrapbox.io/nishio/Over 200 classes were generated) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.