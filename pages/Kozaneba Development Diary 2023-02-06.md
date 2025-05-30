---
title: "Kozaneba Development Diary 2023-02-06"
---

prev  [[Kozaneba Development Diary 2023-02-03]]
- prev  [[Kozaneba Development Diary 2023-01-25]]

Today's Picture of the Day
- ![image](https://gyazo.com/e9c5836b0637cb39eee9531dea9dcfe9/thumb/1000)

- [[Kozaneba:Changes in programming languages in the last decade]]
memo
- Most of the features to draw lines together are not used.
- I feel like we need a version of this that doesn't have arrows on it.
    - ![image](https://gyazo.com/cce3ca581cbc0e6701f0faff0685677a/thumb/1000)
    - There are very few cases where you want to draw a two-part graph in the first place.
        - Draw a line from the leftmost point of the selection to the other
        - Draw a line from the other to the rightmost edge of the selection.
        - I think these two are enough.
        - Or just the former.
- About the function to draw a line with a click
    - If the mouse moves slightly when clicking, it becomes a drag instead of a click and the line is not drawn.
        - I'm a developer, so I understand this, but the average user is going to feel like, "I don't know why I can't draw the line sometimes.
    - So far, "surround and draw a line" seems smoother.
        - Maybe it's just a matter of getting used to it.
        - And then there's the above problem.
- I wish I could rotate the selection 90 degrees.
- I've made a lasso selection as an alternative to rectangular selection, but if the lines are drawn like this, there is also a distance-based selection. If the lines are connected, you can shorten the distance, and if not, you can use the actual distance and select the connected chunks by the distance from the selected kozane.

If you drag a target with ✅ line drawn, it will be dragged properly and the line will also be drawn.
- If I drag over nothing in that state, it selects a range, I'm a little worried that there is a bug in this pathway.
- I'd treat it as cancelled, since the information "in line-drawing mode" is overwritten by the information "in range-selection mode."
✅Improvement of menu to draw a line collectively
- ![image](https://gyazo.com/a8e620d1492be395597e7bc9d64c0af3/thumb/1000)
- ![image](https://gyazo.com/b0759506d00aabdd7a2443b7ab32ac70/thumb/1000)
- ![image](https://gyazo.com/e9c5836b0637cb39eee9531dea9dcfe9/thumb/1000)
- The previous menu was made in symmetry with the top row, but I've never used it and kicked it out because I've never used a "merging double arrow" before.


✅The center of gravity was used to separate left and right, not the midpoint. fixed
- ![image](https://gyazo.com/3b6bcca805f4d6f85ffe9a3d5ca83221/thumb/1000) / ![image](https://gyazo.com/2e9b3c847e118e0bc627eb38decbe9ef/thumb/1000)


Release✅[/kozaneba-forum-jp/release-note](https://scrapbox.io/kozaneba-forum-jp/release-note).

---
This page is auto-translated from [/nishio/Kozaneba開発日記2023-02-06](https://scrapbox.io/nishio/Kozaneba開発日記2023-02-06) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.