---
title: "React+Canvas"
---

[[React]]+[[Canvas]]
- [Using React Hooks with canvas – ITNEXT](https://itnext.io/using-react-hooks-with-canvas-f188d6e416c0)
    - 1
        - Path2D
        - Grabbing and writing raw Canvas with useRef.
    - 2
        - Have user operation logs in useState
    - 3
        - Instead of drawing directly on click, it is drawn with useEffect
            - setX updates the state, so render runs and useEffect is called.
            - Will there be performance issues since all the clicks are being redrawn?
            - > In the current implementation every render first clears the canvas and then draws all the locations. We could be smarter than that, but to keep it simple I’ll leave it to reader to further optimize this.
        - > drawing on the canvas is a side effect determined by the app state
        - Clear is equivalent to delete history, Undo is equivalent to slice
    - localStorage
        - Just save the history.
    - Bundle hooks for state persistence with custom hooks


---
This page is auto-translated from [/nishio/React+Canvas](https://scrapbox.io/nishio/React+Canvas) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.