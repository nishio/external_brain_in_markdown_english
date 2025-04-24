---
title: "Arrange SVGs in the menu bar"
---

SVG can also be embedded in JSX so that it can be a component of React.
It is no different than any other DOM component, especially if you want the props to change color.

tsx

```
export const UndoSVGButton = (props: any) => {
  let color = props.enabled ? "#000" : "#888";
  return (<svg enable-background="new 0 0 24 24" id="Layer_1" version="1.0" viewBox="0 0 24 24">
    <polygon points="9,12 2,7 9,2 " fill={color} />
    <path d="M2,20h11.5c3.6,0,6.5-2.9,6.5-6.5S17.1,7,13.5,7H6"
      fill="none" stroke={color}
      stroke-miterlimit="10" stroke-width="4" />
  </svg>);
}
```


treatment
:

```
<div id="toolbar">
  <UndoSVGButton enabled={canUndo} onClick={undo} />
  <RedoSVGButton enabled={canRedo} onClick={redo} />
  ...
```


I used to do it with text and CSS, but it wasn't beautiful to code or look at.
:

```
<span onClick={undo} className={canUndo ? "canDo" : "canNotDo"}>[Undo]</span>
```

Undo and Redo are still text, but I'll replace them with icons soon.
![image](https://gyazo.com/23cad50452da5b3c77942de52fc9b073/thumb/1000)
Related: [[Vertical Alignment of Text]].

---
This page is auto-translated from [/nishio/メニューバーにSVGを並べる](https://scrapbox.io/nishio/メニューバーにSVGを並べる) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.