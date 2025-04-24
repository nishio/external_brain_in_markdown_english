---
title: "Where to access the instances created in Reconciler"
---

from [[pRegroup-done-2019]]
Where to access the instances created in [Reconciler
react-paper-bindings creates and returns a Raster instance of Paper.js in Reconciler's createInstance
- Where can I access the object returned here?
- [https://github.com/react-paper/react-paper-bindings/blob/50c16e349b0ceb1bf06c08de0ef7981b02985bf6/src/PaperRenderer.js#L317](https://github.com/react-paper/react-paper-bindings/blob/50c16e349b0ceb1bf06c08de0ef7981b02985bf6/src/PaperRenderer.js#L317)
- I guess I need to look into React's Reconciler specs for this one.
    - (The return value of <Raster> in JSX was of course not this instance itself, but an object created by React.)
- Passing references to external variables with ref
    - [How to Get a React Component's Element](https://davidwalsh.name/get-react-component-element)
- Some commentaries interpret [[ref]] as a "reference to the DOM," but it is not a reference to the DOM, but to an object created in the Reconciler, which in the context of creating a web app is simply the DOM.

---
This page is auto-translated from [/nishio/Reconcilerの中で作られるインスタンスはどこでアクセスするか](https://scrapbox.io/nishio/Reconcilerの中で作られるインスタンスはどこでアクセスするか) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.