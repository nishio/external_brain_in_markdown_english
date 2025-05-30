---
title: "Kozaneba Development Diary 2021-08-31"
---

from  [[Kozaneba Development Diary 2021-08-30]]
2021-08-31Kozaneba Development Diary

- [[ReactN useGlobal can fire even if the reference does not change.]]
- [[Make a change diff and setGlobal]]

[[Over 200 classes were generated]]

In Firefox, `navigator.clipboard.readText === undefined`, so `prompt` is issued.

![image](https://gyazo.com/677d8dafc846263acb5e4bf05238db04/thumb/1000)
User extensions can now add menus.
`kozaneba.user_menus.Kozane.push({label: "hello", onClick: ()=>{ alert("hello!") }})`

release notes
2021-08-31
- When you paste in a browser that cannot read from the clipboard (e.g. Firefox), you get a prompt instead.
- User scripts can be added to the menu.

Performance is better now that the excessive screen redrawing has stopped, but we probably find that we forgot to refresh the screen in a few places (like not refreshing when closing a group).
- No, this is not a "maybe I'm forgetting something" thing, it's a big no-no. Let's cut it back and fix it properly tomorrow.

Cut back to yesterday's stage
![image](https://gyazo.com/e6e6759e11afd9f50ab66c229d90c61d/thumb/1000)
Easy and convenient

---
You don't want this kind of slapstick in your release notes.
:

```
2021-09-01
　unreleased
　　Fixed a bug that prevented redrawing for updates that did not change the drawing order (e.g., opening and closing groups)
　　　(It is also strange that the drawing order is not updated by opening and closing groups in the first place.)

2021-08-31
　unreleased
 　When you paste in a browser that cannot read from the clipboard (e.g. Firefox), you get a prompt instead.
 　User scripts can be added to the menu.
　Resolves excessive screen redrawing
　　The performance is better, but you'll probably find that you forgot to update the screen in a few places.
　　→ Not updated when group is closed
　I cut it back to yesterday's stage.
```


It is also strange that the drawing order is not updated by opening and closing groups in the first place.
- modified drawing order is updated by opening/closing groups
    - Policies that will be at the forefront of what you edit.
> Fixed a bug that prevented redrawing for updates that did not change the drawing order (e.g., opening and closing groups).
- What else is an update that doesn't change the drawing order that should be redrawn?
- Style with API
    - That should also be at the forefront.

clean copy
- 2021-09-01
    - Open/close group to move group to the forefront
    - Move to the front of the line with style settings in API
    - Fixed a bug that the position was shifted when a group was moved from
    - Changed the specification that there is a discrepancy between the position on the screen and the position inside when moving in and out of groups
        - Expect a little more updating cost, but no more mysterious discrepancies.

- 2021-08-31
    - When you paste in a browser that cannot read from the clipboard (e.g. Firefox), you get a prompt instead.
    - User scripts can be added to the menu.
    - Resolves excessive screen redrawing
        - The performance is better, but you'll probably find that you forgot to update the screen in a few places.
    - Bug that does not update when group is closed.
        - I cut it back to yesterday's stage.

I think that when I drag the kozane slightly, it sometimes jumps in a direction perpendicular to the direction it was moved.
- If you move it right after that, it will be displaced in the opposite direction.
- At this time, top or left is missing from the style
:

```
Foo = styled.div`... Sometimes, when I do <Foo style={style}> for `Foo`, only one of the two is attached to the actual HTMLDivElement even though style: {top: number, left: number}.
```

- Why?

- [[Kozaneba Development Diary 2021-09-01]]
---
This page is auto-translated from [/nishio/Kozaneba開発日記2021-08-31](https://scrapbox.io/nishio/Kozaneba開発日記2021-08-31) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.