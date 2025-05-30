---
title: "Bug that breaks if you zoom out as far as you can."
---

from [[pRegroup2020]]
Bug that is fine when zoomed out somewhat on the iPad, but breaks when zoomed out drastically.

- This is another violation of SINGLE SOURCE OF TRUTH.
    - There is a discrepancy between the zoom value that Paper has and the zoom value that React has.
    - This is a case where zoom needs to be changed directly without React state update for smooth zooming.

- A minimum value was set for ZOOM to prevent it from becoming too small when turning the wheel or doing a two-finger gesture on the PC version.
- The PC version updates React with the Paper value in setTimeout 500msec after the wheel event occurs, so the values remain consistent.
- On the other hand, the iPad version updates both Paper and React by itself at the end of the two-finger gesture.
    - At this time, the "minimum value" is applied only to Paper updates, and a different value is set
    - There is a pathway where the ZOOM value becomes NaN when further changes are made in that situation.

- It's rather ugly, but I managed to get away with inserting a similar minimum value process where the React update takes place.
- We'll fix this together when we clean up and redo the state transition area after the CCSE.
        - [[Reduxing]]

- Essentially, the maximum and minimum value processing should be determined based on the device information
---
This page is auto-translated from [/nishio/思いっきりズームアウトしたら壊れるバグ](https://scrapbox.io/nishio/思いっきりズームアウトしたら壊れるバグ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.