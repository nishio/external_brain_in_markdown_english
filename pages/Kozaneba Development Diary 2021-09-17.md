---
title: "Kozaneba Development Diary 2021-09-17"
---

Not much of a development diary this week, because we're not using the user-friendly features.

What we did.
- Reduce oscillations in physics calculations
- Move unpin to the add user menu instead of the system menu
    - Physics itself is still an experimental feature that can be added and used by user scripts.
- Created an API for adding arrows and added the ability to pull arrows together in a user menu.
- Create server API to hit kintone API
    - Delete this once
- Adjust position and color of link icons
- Created a demo that taps the kintone API to create kozane
- Added server API to create places
- Browser extension to create Kozaneba's Ba from kintone's record list

release notes
- Reduce oscillations in physics calculations
- Move unpin to the add user menu instead of the system menu
    - Physics itself is still an experimental feature, added and used by user scripts, so it is misleading that it is displayed even to those who have not added it.
- Create arrow add API
    - Added the ability to pull arrows together in a user script.
    - ![image](https://gyazo.com/db24cc8fbda75c98c436458fb4fcf5fc/thumb/1000)
- Adjust position and color of link icons
- Added server API to create places with JSON


2021-09-17
- Add the double-headed arrows to the menu because they are used so often.
    - In addition, the arrow addition menu up to now also clearly states that right is head.
- Fixed an error when an element was removed from a group without a title with an arrow and the group was automatically deleted


---
This page is auto-translated from [/nishio/Kozaneba開発日記2021-09-17](https://scrapbox.io/nishio/Kozaneba開発日記2021-09-17) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.