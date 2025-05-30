---
title: "Write down and organize the functions of Regroup"
---

from  [[Regroup to Movidea]]

2021-06-16
- [[I want to give the new version of Regroup a different name.]]
- [https://regroup.netlify.app/#/key=4oi8PjusZO8KoxMw8H8p&cx=1841&cy=545&top=-2612&left=-3807](https://regroup.netlify.app/#/key=4oi8PjusZO8KoxMw8H8p&cx=1841&cy=545&top=-2612&left=-3807)
- ![image](https://gyazo.com/1f7e7eb2729a0a3288ad531d7a4d83bb/thumb/1000)
- What is important is not the "grouping" nor the "folding function" but the "[Ignore the branches and leaves and concentrate on the higher level structure.
- I told my wife, "I'm thinking of making a version with minimal features," and she said, "It was overkill to implement the ability to change pen color, thickness, and dotted lines, and I'm thinking of making it like a whiteboard marker with black, red, and blue once I'm done. He said, "You don't need the pen function in the first place?
    - that may be true
    - The main purpose is to do something like "this and this are in conflict" with each other by enclosing or using arrows after arranging stickies, whereas [[Too much freedom...]].
    - Why not just have stamps?" They said, "We have already realized image stickies, so we should have a "palette of frequently used stickies".
        - ![image](https://gyazo.com/9fadf7bedc6413921eb7d14630a7f13a/thumb/1000)
    - If you throw away the full handwritten-add-on feature, you can throw away the lasso selection as well, and HTML5 Canvas will no longer be necessary.
    - If what you really need is to enclose, the current grouping display already achieves that, and if you want to describe relationships, a connector may be more appropriate (since you can move stickies after drawing them).
- Important Features
    - Sticky notes can be added.
    - Stickies can be moved.
        - Stickies can be moved together.
    - Smooth screen zooming

Grouping is not good in its current form.
    - [[Is the folded group the size of one sheet?]]
- grouping
    - I use it a lot to put things together, but I don't fold it much, I don't know why.
        - Making a nameplate is a pain in the ass.
        - Dragged from the physical KJ method, the sticky note is the front page.
        - hence
            - Make a sticky note with a summary
            - Make a group with it in the upper left corner.
            - close (a shop)
        - requires a procedure called
        - But the first thing I do is "create a group".
            - Whether or not you will want to fold is undecided at the stage of creating the group.
            - When you want to fold it up, you say, "I'm not going to know what it is because I didn't keep the nameplate neat when I folded it up."
                - I'm not inclined to dismantle it and rebuild the nameplate.



It's not a good idea to be able to move the selected object by itself while the lasso is selected.

Should fold correctly when the group is put into further groups.

The pen function is dead.
- It's very annoying when you're trying to put together a presentation and you discover something like this, and you don't have time to fix it.
- I still need a regression test.

[/shokai/Scrapbox development process](https://scrapbox.io/shokai/Scrapbox development process).
> Elements that will lose impact
>  Close to something you've seen somewhere else.
>  The idea that the more functions, the better.
>  Lots of bugs

The ability to change the color of the pen took a lot of code to create, but it wasn't necessary.
- I created a dialog, but...
- One black color or, if more, red and blue would be sufficient.
- Dotted lines? Translucent? How thick?
    - Do you want to add UserScript functionality for such details?

Ensure stable use with minimal functionality

The idea of stiffing co-editing is on hold.
- While there is potential for interesting uses, the priority is to cover the uses we can see now with the minimum amount of code.
---
This page is auto-translated from [/nishio/Regroupの機能を書き出して整理](https://scrapbox.io/nishio/Regroupの機能を書き出して整理) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.