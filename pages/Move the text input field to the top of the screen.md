---
title: "Move the text input field to the top of the screen"
---

![image](https://gyazo.com/33249161f11ed1793c717c634a07533a/thumb/1000)
- Auto zoom in on text area when entering sticky mode on iPhone
    - That can be avoided by setting the font size to 16px
- When I try to enter text, it scrolls to the text area by itself.
    - I don't know how to work around this.
- When I think about it, I realize that Scrapbox also had a modal text area at the top of the page when it was served.
    - Could this be unavoidable behavior?
- Do you want to design a text area around the toolbar?
- I tried.
    - There was a hypothesis that it might be better not to afford multiple lines of text input, so I made it look like a single line of text.
        - (actually textarea)
- I feel like this is the right thing to do.
    - I tried once to put it right under the toolbar, but that would put the text bar over the sticky.
    - I wonder if it would be better to put it right over the toolbar, so that it would not be an unnecessary operation while entering text.
        - I hid the UNDO, but...
- It is strange that the arrow on the icon meaning OK is pointing up when the input field is in this position.
- To begin with, I want to change the behavior of [[Add a sticky note with a new line]].
        - [[I'd prefer to see more and more stickies added to the line breaks.]]

----
- The following problems seem to have been almost eliminated by moving the text area, so we'll see how it goes
- ![image](https://gyazo.com/3caad9f4f44947f712fc34fc8ec3ca5f/thumb/1000)
    - Rotate the screen on iPhone and iPad so that the display does not go haywire.
        - When in sticky note input mode on iPhone, the text area size designed for iPad is too large
            - I lose track of the toolbar because of that.
    - The menu bar is hidden when the screen is rotated, for example.
    - TODO: Tap on a white area with no canvas to reposition it to the proper position!
        - Or Shake
    - I don't want to have to hide in the first place.

[[pRegroup-done-2019]]

---
This page is auto-translated from [/nishio/テキスト入力欄を画面上部へ](https://scrapbox.io/nishio/テキスト入力欄を画面上部へ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.