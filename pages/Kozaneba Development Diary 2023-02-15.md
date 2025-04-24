---
title: "Kozaneba Development Diary 2023-02-15"
---

prev  [[Kozaneba Development Diary 2023-02-06]]

[[Kozane-clone-tear-merge]]
- As a result of many lines being connected to a certain kneeling position, that kneeling position will not sit well wherever it is placed.
- Automatic layout of graphs, for example, places such an element in the center and creates a display that surrounds it.
    - That would be, in essence, a fancy, degraded version of the MOST LINKED order sort, only in appearance.
- What we need is when we find an "element with too many dense lines".
    - This is overly abstract, so it's attached to a lot of things, isn't it?
        - [[Be more specific.]] Can't you?
    - Can you narrow the scope?
    - Can you increase the resolution?
- Helping people to think about

Maybe you could add the following to the group's menu
- Rotate right, rotate left
    - Maybe just one of them.
- spread around
    - Use when margins are insufficient.

Import from Scrapbox
- Importing more than 1000 pages shouldn't be done anyway because nothing human can do about it.
- Specify the starting page and follow the n-hop links from there to import
- Rather follow a random link and import?
    - That sounds interesting too.
    - Specify 25 or 100 items to be read until the specified number is reached or the timeout occurs.
    - I feel like that's what EXPAND is doing now too.
- Approach to do from exported JSON
    - I don't see a written explanation of Kozaneba's JSON import function.

What I didn't do.
- Kozane bounding box without font size adjustment
- Merge with what you have already imported when importing from Scrapbox

- [[Import Scrapbox projects into Kozaneba (Development)]]
- [[Discussion of ChatGPT and hairball unraveling]]
- [[Experiment with importing Scrapbox projects into Kozaneba]]

memo
- > Merge with what you have already imported when importing from Scrapbox
    - This is a lower priority.
    - I was envisioning a two-hop deployment situation, but it would be messy.
    - Rather, "[[when expanding from one page, draw a line from the center, but not from the siblings]]" is the priority.
- [[Kozane-clone-tear-merge]]
    - This is very time-consuming to try to achieve in any other way.
    - feel the need


---
This page is auto-translated from [/nishio/Kozaneba開発日記2023-02-15](https://scrapbox.io/nishio/Kozaneba開発日記2023-02-15) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.