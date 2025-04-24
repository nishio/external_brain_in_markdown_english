---
title: "Zoom with full view when loading editor"
---

relevance
    - [[Whole view button]]
from [[pRegroup2020]]
Zoom with full view when loading editor
- I'd like it to be zoomed in so I can see the whole picture first when it loads.
    - Not much use for initial zoom.
    - On the other hand, it's not a good idea to save the user's last zoom and position.
    - I still think it's good to see the whole picture.
- Default value if not explicitly specified
    - If specified: [[View sharing link]].
    - Doing this actually requires a bit of work.
        - Because the content hasn't finished loading at the time the URL is interpreted.
        - The handler "Display the entire contents when the content has finished loading" will be set up.
            - [If the coordinates are not specified, the whole display first.


- Zoom where you can see the entire sticky, surprisingly, it becomes too small if you do "calculate the unite of bounds of all elements and compare it with the current view.bouds and set the scale", and if you consider the pixelRatio, it gets decently close, but not exactly right, so I have a feeling there is some kind of misunderstanding. I think I'm getting it wrong somehow.

---
This page is auto-translated from [/nishio/編集者のロード時は全体が見えるズーム](https://scrapbox.io/nishio/編集者のロード時は全体が見えるズーム) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.