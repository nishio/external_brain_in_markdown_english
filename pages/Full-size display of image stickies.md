---
title: "Full-size display of image stickies"
---

    - [[Display images on stickies]] Now I can do that.
- Small because it is treated as a sticky note
- Sometimes I want it bigger.
- Behavior is similar to "Open Group
    - Folded groups are the size of sticky notes
    - The group that opens is the size of the content inside
- Groups with only paths will be displayed as thumbnails when closed.
    - Close to this.
- So do you want a group?
    - No, that's not right.
    - It's odd to make a group just because it can be opened and closed when it has no child elements.
    - I'd rather only groups be able to open and close because the need for opening and closing came up first in groups, and stickies can wait to switch between "thumbnail view/detail view" as well.
    - Simple text stickies just don't have anything to display details.
        - When the content is long, the full text can be displayed in detail view at a certain font size, or only the small text or the beginning of the text can be displayed in thumbnail view.
- in other words
    - Full-size display of image stickies
    - Full text display of long stickies
- This means that the stickies need a mechanism that allows for
- Add compact:bool to sticky object, data without it is considered true
    - False when adding image stickies
        - But this is identified as an image sticky when it's drawn, so I'd hate to rewrite the start there.
        - It's not right to parse text every time when drawing.

In the future, there may be a need for "[The original size image is too large and I want to scale it up or down.

Implemented.
- ![image](https://gyazo.com/7d26957b13b1437d8020a0aae9ead5b3/thumb/1000)


- I thought I needed to add [[Menu to collapse images in full size display]], but since I don't need it now, I'll hold off.

[[pRegroup-done-2020]]

---
This page is auto-translated from [/nishio/画像付箋の原寸表示](https://scrapbox.io/nishio/画像付箋の原寸表示) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.