---
title: "20180726 What we did"
---

    - [[Multi-slide highlighting]]
    - I'm using one "red board" right now to achieve the highlighting, but should I make one for each slide or is there a better way...
    - I got as far as creating the object with the red border and adding it to the child objects.
    - No way to access the child from the object
    - Should there be a MonoBehavior to represent slides because I want to store children, indexes, file names, etc.?
    - →Created a non-MonoBehaviour class to represent slides.
            - [[Refactoring 20180726]]

- Time measurement of multiple selections
    - Check if it is safe to do every frame
        - Use [[Status display on controller]] to display FPS.
    - → I made one that gives out the FPS in Debug.Log.
        - I prefer the controller status display because the logs drift away.

---
This page is auto-translated from [/nishio/20180726やったこと](https://scrapbox.io/nishio/20180726やったこと) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.