---
title: "ReGroup2018"
---

- Project to improve self-made electronic KJ method tool
    - Homemade electronic KJ method tool grouping] that I made about 5 years ago and neglected.
    - I thought it would be rather good assuming iPad Pro + Apple Pencil, so I restarted ([[2018]]-09-19)
    - Development code name [[Regroup]]

- [[Development on iPad]]

- I'll use Pencil for editing.
- Overlap order issues in SVG
- Store data in Cloud Firestore

-----
- I checked the [Google Realtime API](https://developers.google.com/realtime/overview) used in previous versions for porting and it says it will end next January.
- [Select Database: Cloud Firestore or Realtime Database | Firebase](https://firebase.google.com/docs/database/rtdb-vs-firestore?hl=ja)
- [Cloud Firestore Data Model | Firebase](https://firebase.google.com/docs/firestore/data-model?hl=ja)

- Data structure of previous versions: `[{text, when, id, x, y}]`
    - Grouping and arrows were unimplemented save functions.
    - It would be interesting to be able to see the working process later, so it would be good to [[Save history of changes]] in the form of history.

- [10 points to keep in mind when developing medium to large scale SPA - KAYAC engineers' blog](https://techblog.kayac.com/10-spa-knowhow)
    - What is client-side routing?
        - [SPA routing story](https://www.slideshare.net/ushiboy/spa-76170499)
        - It's like what they used to do at Hash is becoming more sophisticated.
    - [Front-end development doesn't need Babel or Webpack * - KAYAC engineers' blog](https://techblog.kayac.com/pure-js-app)
        - importable
            - [import - JavaScript | MDN](https://developer.mozilla.org/ja/docs/Web/JavaScript/Reference/Statements/import)

- [Enable Offline Data | Firebase](https://firebase.google.com/docs/firestore/manage-data/enable-offline?hl=ja)
    - Later.

- [[Firestore]]
-----
The React version does not cause the text to disappear on touch when displayed on the iPad, so it must be an issue with the older version of Raphael.

-----
- Create a new version for my own use on iPad Pro.
    - Make the UI suitable for the iPad
        - [[Zoomed-out overall view mode by default]]
- design guideline
    - Must be meaningful when zoomed out [[Make the display meaningful when zoomed out]]
        - The display is meaningless if all you can see is "Wow, there's a lot of stickies.
        - Set a lower limit for font size and hide text that is smaller than the limit, judging that it is not human-readable.
        - Use the large display space created by this to zoom in on advanced sticky titles such as nameplates
            - The image is that of SimCity, where place names, etc. are displayed when the entire map is displayed.
        - [[Must be able to notice things off screen when zoomed in view]]
    - Groups don't have to be explicitly created.
        - Explicit group affiliation relationships require in, out
        - When moving in batches, you can specify which one is to be folded for the first time when folding.
        - The target to be moved collectively is not necessarily a group.
- [http://nishio.github.io/idea-generation/grouping/#fileIds=1cED4uxHbS3ylaD13-X3sNnyV4dDbnq83&userId=112643481944466832095](http://nishio.github.io/idea-generation/grouping/#fileIds=1cED4uxHbS3ylaD13-X3sNnyV4dDbnq83&userId=112643481944466832095)

-----
- At the time it was created, the screen was too small to be practical.
- I opened it on my iPad Pro and confirmed that it works.
    - Zooming out is not accepted immediately after opening (it transitions to tabbed view).
    - If it is zoomed in, it can be zoomed out.
    - Zoom in and parallel movement can be performed with the two-finger gesture.
        - →Can I zoom out to where I can see the entire sticky when I open it, and then zoom in and use it from there?
    - Stickies can be moved by finger or Pencil.
        - However, there is a mysterious phenomenon where the text disappears when the text portion is dragged.
    - By default, 100 cards are lined up tightly to fill the screen.
        - But even if you double the height and width, you can still read quite a few words.
        - If you can zoom in and out smoothly and intuitively, you can go far enough.

- Extra features
    - The current version has [[Ability to write arrows]] etc. between boxes.
        - What is really needed in doing KJ method electronically is support for "group formation".
        - Arrow additions, etc., should be done in the A-type diagramming process after grouping.
        - Arrow functionality is not necessary for the grouping phase, confusion caused by having many menus is detrimental
        - Debugging UI for developing on a PC is cluttering up the bottom.
            - When I open it on my iPad, I see it by default.
            - It would be better to hide this at first and have it appear when you press the development menu.
        - To illustrate, you can take a screenshot or export an image and use the iPad's own functions to write on it.
            - Should there be PDF export?

- Missing features
    - Make the image a sticky note
        - I think the approach of interpreting a sticky as an image if its content starts with http is fine.
    - grouping
        - You can use "Bundle mode start button→tap (toggle) the target sticky→done button/cancel button".
        - I just created a lasso tool and it has the same number of moves as "lasso mode", "selection", and "grouping".
        - procedure
            - Bundling mode starts
            - Tap the target sticky
            - Finish button
            - Select a nameplate or create a new one

---
This page is auto-translated from [/nishio/ReGroup2018](https://scrapbox.io/nishio/ReGroup2018) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.