---
title: "Create shared links with embedded coordinates"
---

aka  [[View sharing link]]   [[Specify viewport by URL]]

- I should be able to share with others what I see.
- The aspect ratio is different from the counterpart.
- So, embed the Rectangle in the URL and make the Zoom capable of displaying that Rect
    - Center is fine as is.
- Pass Center to Zoom" is inconvenient when passing a large screen view to the iPhone.
- `&cx=155.20097005175816&cy=-159.15570591146707&left=-231.88275288159716&top=-847.4105222489367`
    - With a specification like this, the zoom is now calculated and displayed in such a way that the topLeft point fits within the screen.
        - If only cx,cy are specified, the standard 1.0 zoom is used and only the center is adjusted there.
    - Now we just need to implement the part where we create this URL from the current view.
    - done

--- Discussion of July below
Create shared links with embedded coordinates
As a use case
- Show others what the editor has created.
    - The viewer defaults to zoom, so the first thing you're going to say is, "Wow, how do I see that?" they'll be like, "Wow, how do I see that?
    - I knew it was "Zoom to see the whole picture by default".
    - Or, the editor should be able to share the link with the zoom that the editor can see when he/she shares the link.
- →"Zoom to see the whole picture" is not good enough.
    - What you want to show is not always the whole picture.
        - Close up of part of a larger map
        - Don't show unorganized sticky notes tucked away on the edge.
        - Don't show trash sticky notes.
    - Just use the "Create Shared Link" button to create a URL with the current coordinate system embedded.
- Is it necessary in the first place?
    - From the point of view of those who "just watch."
        - In the first place, if you are given something that is in a locally editable state...
        - I'm nervous that I might have accidentally edited and "broken it".
        - Need to read manual for operation.
        - Maybe it's better to be shared in an image.
    - Group availability is significant.
        - If there's no group, it's just a two-dimensional arrangement of stickies, so you can share it with images.
        - With the group folded, the image does not show the back of the group.
            - [[If you don't have a closed group, just use a picture.]]
            - Conversely, "[[Close Group]]" = "[[compress information]]" is the key to providing value that has not been possible with images.

[[pRegroup-done-2020]]
---
This page is auto-translated from [/nishio/座標を埋め込んだ共有リンクを作成](https://scrapbox.io/nishio/座標を埋め込んだ共有リンクを作成) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.