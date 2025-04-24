---
title: "Improved style change UI"
---


- I want an after-the-fact style change.
- Change "Current Style" from the menu
- Change the style after the fact] after the selection
- Right now it's a text menu, but I'd like to make it graphical.
- Should be the same for both pathways.
- Create a dialog
- Better to paint on canvas than to work hard on DOM, unity of appearance
- When I select a pen and change the style, does the current pen color change as well?
    - If that is OK, then the "current style" change can be a style change for an empty selection.
    - Let's just follow that policy for now and get a dialog from the balloon menu after making a selection.

![image](https://gyazo.com/66d7472a36eeee3981d3bb22ee02bfae/thumb/1000)


- We made it this far.
    - Semi-transparency (used for marker-like emphasis) and dotted lines still don't work well together.
    - In the first place, the transparency is not a style, which is a specification of PAPER.
    - I didn't save it on the server, or something.
    - It's a bit of a mess, like it looks different when you're tangled up in those things, but then you reload it and it goes back.

    - [[Semi-transparent and dotted lines]] Got it.


- In the future [[The style you are currently selecting should be visible on the screen.]]


![image](https://gyazo.com/b1ce4b7dc69d47c00c38a5bf6f9be75c/thumb/1000)
---
This page is auto-translated from [/nishio/スタイル変更UIの改善](https://scrapbox.io/nishio/スタイル変更UIの改善) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.