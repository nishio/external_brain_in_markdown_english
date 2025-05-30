---
title: "Creating SVG icons in Adobe XD"
---

Creating [[SVG]] icons in [Adobe XD
- Selection can be exported.
- Group them into one.
    - If you select multiple objects without grouping, they will be output individually using the object name without specifying a name, so
- You can make a white rimless box of the desired size, center it with the array tool, and group it.
    - Simply exporting will output with bounding box size
    - Adjusting size and placement afterwards is a hassle.

![image](https://gyazo.com/a16b20bf64b060534600631a7621ac17/thumb/1000)

Since it is SVG, it is easy to change the style programmatically.

ts

```typescript
export const LassoSVGButton = (props: any) => {
  const strokecolor = isActive(window.app.paperLassoTool) ? "#00C" : "#777";
  const strokewidth = isActive(window.app.paperLassoTool) ? "3" : "1";
  return (
    <svg onClick={props.onClick} viewBox="0 0 50 50">
      <rect x="5" y="5" width="40" height="40" rx="10"
        fill="none" stroke={strokecolor} stroke-width={strokewidth} stroke-dasharray="5 2"/>
    </svg>
  )
}
```




---
This page is auto-translated from [/nishio/Adobe XDでSVGアイコンを作る](https://scrapbox.io/nishio/Adobe XDでSVGアイコンを作る) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.