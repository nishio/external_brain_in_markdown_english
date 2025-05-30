---
title: "Lasso selection of stickies and paths"
---

from  [[Sticky note selection and compression UI design]]
- [[Lasso selection of stickies and paths]]
- Draw a path with thin lines
    - It is essential to separate layers that are updated frequently
            - [[Faster Drawing]]
- if you let go
    - Highlighting selected items?
        - At any rate, this one looks easier.
        - [[Dotted line display of selection]]  done

- CD
    - ×x hitTest from each point of the selected path
        - →The inside of the path is not selected.
    - Stickies are 4 corners, paths are hitTest from each point to the selected range path
        - The more objects there are, the heavier it is going to be.
    - Proposal to use path and path boolean operations
        - [https://stackoverflow.com/questions/40706454/paper-js-lasso-select-tool](https://stackoverflow.com/questions/40706454/paper-js-lasso-select-tool)
        - This is simple, but there are performance concerns.
            - I'd implement it without worrying about it for now, and if it's too slow, maybe narrow it down with a bounding box first!
            - It looks like they are already doing it internally!
    - [https://github.com/lsst-epo/paper-select-tool/tree/master](https://github.com/lsst-epo/paper-select-tool/tree/master)
        - This is just "hitTest at each point of the given Array({point: Point})
    - → First, let's try to implement it with boolean operations.
        - Verify that it runs fast enough
        - 100 sticky intersect runs 20msec on iPad.
        - The hit detection in the case of full inclusion instead of intersect does not work well with the planned boolean operation.
            - This is probably because while intersects are defined for Path and Shape
            - The implementation assumes that subtract is Path and Path
            - I guess the method that arg called internally thinking it was Path is dead because it doesn't exist.
        - cope
            - If the shape is fully contained, a hitTest at a point relative to the center of gravity of the shape will definitely hit the Path if the opponent is a Shape.
            - If subtract can be used when the other party is Path, then there is no problem.
            - The path must be filled, so clone and fill with opacity: 0.
        - The percussion between the sticky and the sticky works fine now.
        - It also moves to determine if it hits a pass or not.

![image](https://gyazo.com/e79d134ca70f1b4999bf0ce6cd03f9e9/thumb/1000)

- (Low priority) [[Lassoing selected items together and moving on.]]
- (Needed?) Selection minus function

[[pRegroup-done-2019]]

---
This page is auto-translated from [/nishio/付箋・パスの投げ縄選択](https://scrapbox.io/nishio/付箋・パスの投げ縄選択) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.