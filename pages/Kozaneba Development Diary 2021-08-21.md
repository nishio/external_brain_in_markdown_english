---
title: "Kozaneba Development Diary 2021-08-21"
---

prev  [[Kozaneba Development Diary 2021-08-20]]

js

```javascript
localStorage.setItem("onLoad", "console.log('hello')")
```

User can define scripts to be executed at load time

    - Users can override the behavior of the tutorial when they access the top page.
    - Users can add buttons to the AppBar

Bug not usable on touch devices.
2021-08-23 <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I'm trying to fix it, but it doesn't seem like an easy fix.
[https://twitter.com/nishio/status/1428904779703472131?s=20](https://twitter.com/nishio/status/1428904779703472131?s=20)

> Usually, we can use `overflow: hidden` on the <body> element to prevent scrolling. But unfortunately, that does not work on older versions of iOS.
- [Simple Solution to Prevent Body Scrolling on iOS - Markus Oberlehner](https://markus.oberlehner.net/blog/simple-solution-to-prevent-body-scrolling-on-ios/)

It's hard to get the iPhone to work as expected.
- Aside from the iPhone, I'd love to see it work on the iPad.

---

When I think about running Scrapbox cards on Kozaneba, I need to be able to create something that behaves like Kozane but has a different DOM structure.
- This "same behavior" is also ambiguous.
- Ideally, this could be accomplished with user extensions, but that's [[You're trying to solve two problems at once.]]

---

2021-08-23

I'm always tempted to do "something I haven't done yet".
Already doing it, and almost prioritizing it over features that were useful.
Getting it to work on the iPad is a muddle.
If I can get it to work on my iPad, I'll be tempted to add handwritten additions.
SVG of handwritten additions
anchor point
Auto-positioning objects

![image](https://gyazo.com/59a3112074719fb8922802a663c939a5/thumb/1000)
![image](https://gyazo.com/d7a9ad76fabdfd867c14497827967780/thumb/1000)
I wrote the dependencies with red arrows, but since one-way updating will cause circular references, it would be better to use the gradient method to solve for each point as a "constraint that minimizes the distance".

Thumbnails on links for sharing


Instead of skipping tutorials, just make the first process user-customizable.

paste
- Paste JSON
    - →Determine format
        - Regroup
        - Kozaneba
- Text Paste
    - Open Add Kozane Dialog
- Paste Image
    - Upload to Gyazo and make it Gyazo Kozane
        - First, you need a Gyazo Kozane
            - Allow switching of rendering methods in Kozane's options
            - It would be nice to be able to extend it from the user in the future.
        - Is this a "kozane" in the first place?
            - GroupItem, KozaneItem, should not be lined up at the level of
            - In other words, "add item.type"

read-only sharing
- thumbnail view

Let's lose the "tutorial" in the menu ✅.

The wheel and touchpad can be used individually to set the speed when zooming.
- The distinction between a wheel and a touchpad, the deprecated property is a wheel, and the typical device is 120, which is used for identification and so on (discussion in 2020).
- [Detect touchpad vs mouse in Javascript - Stack Overflow](https://stackoverflow.com/a/62415754/3651086)
- The implementation itself is not difficult, so I can put it out there with enough confidence to say, "I think it works for now.
    - done


![image](https://gyazo.com/4d804026c6f5a45f2ae61d6692f22f7f/thumb/1000)

Dragging a closed group out of position.
![image](https://gyazo.com/7518e22178b2f14a79dbb6f4da996cca/thumb/1000)

No problem when a group is open to move in and out of another group, but when it is closed to move in, it is out of place A
- At this time, "the position when closed" and "the position when opened" are misaligned, so if you return it to the position you wanted to place it in while it is closed, it will be misaligned in the opposite direction from A when it is opened.
- At least I fixed half of the problem: "when you put a closed group into a group, it's out of sync with the open group".
- Apart from that, "things go wrong when you move things around in a group" happens.
- Well, I think I can make it look consistent, but I don't know the root cause of why the discrepancy is occurring.
- Oh, this happens even if it's not a closed group. It's the movement within the same group that makes it go wrong.
- Fixed.

cause
- The contents of the group are offset by the group
    - However, when drawing closed groups, this value was not referenced, so the display is misaligned only when the group is placed inside a group.
- Positioning is wrong only when dragging within the same group.
    - Only occurs when mousemove is generated on a group while dragging, which naturally occurs in user operation, but did not occur in the test code.
    - The structure of the DOM changes when entering and leaving the group, this does not happen at this time.
    - The top-level move is the phenomenon in question itself, but it looks the same because you're not in the group and the offset is zero.
    - Rewriting ReactN state with mousemove event while dragging is expensive and choppy
        - So I was editing DOM styles directly.
        - This style remains even after redrawing by React
            - Because redrawing from React updates the styled-components style, but this is applied to the element via the class, so it has lower priority than the "style of the element itself
            - Once the "style of the element itself" is set, that takes precedence.
    - Insert empty string because style cannot be DELETE
        - I didn't see where it stated that this could be removed.
        - In this case, if you try to parseFloat the value on the next drag as the start position of the drag, you will end up with NaN.
        - [Window.getComputedStyle() - Web APIs | MDN](https://developer.mozilla.org/en-US/docs/Web/API/Window/getComputedStyle)

![image](https://gyazo.com/6df22125da66b4ad8eb7d3a04dc19cd8/thumb/1000)
I see you can produce such a diff (I understand the indentation and still understand the correspondence).




---
This page is auto-translated from [/nishio/Kozaneba開発日記2021-08-21](https://scrapbox.io/nishio/Kozaneba開発日記2021-08-21) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.