---
title: "2021-07-13Movidea Development Diary"
---

Today's Picture of the Day
![image](https://gyazo.com/fea4976e7cd0970fa2d6215de931307d/thumb/1000)

---
- [Update with immer and test with Cypress
Update group position
- ![image](https://gyazo.com/b520f31bbd2876a31557b797babf2f5c/thumb/1000)

Update position of child element B
- ![image](https://gyazo.com/99871fd7fe10311a4a3875a0ac5f80c6/thumb/1000)![image](https://gyazo.com/d2b5c8f049f9f252252391a7cb636044/thumb/1000)

What should happen when a child element is moved after the group is created?
Currently, bounding boxes are drawn properly, but the offset of child element drawing is misaligned.

A: One solution is to "modify the parent's POSITION when the child element moves
- It looks muddled, but it's actually straightforward, because the position of the child element has changed and the center of the parent element has moved.
- Of course, the group could be nested, so it needs to propagate upwards.

B: There is also a way to adjust at rendering time
- We know that the center is not zero when we calculate the bounding box of the child element, so we can shift the offset.
- In this case, the "position" of the "center" group of "child element center" on the screen is misaligned, so it is not folded in the center when it is folded.
    - You could update the position when it's folded, since it needs to be updated to the folded state anyway.

This is something that will be needed after "drag and move child elements after creating a group" is implemented, so let's hold off and move on.

Margin if titled
- ![image](https://gyazo.com/6fb2cd2980e2072a0d88e675287b8bd3/thumb/1000)
- ![image](https://gyazo.com/fea4976e7cd0970fa2d6215de931307d/thumb/1000)
- Hmmm, this is below.

I had the border white in Regroup.
- ![image](https://gyazo.com/47a2059d82ea2ca650b8778f12f81916/thumb/1000)
- I'm not sure if this is the right way to go when it comes to titles.
- Expression especially when closed
    - ![image](https://gyazo.com/cd39735c6207503682585bd6c0cf71fa/thumb/1000)![image](https://gyazo.com/527ca94b74a14ac4f5dc59a9e63ae9a6/thumb/1000)
    - By leaving the border, we're expressing that we're a group, so if the border is white, it's hard to tell us apart.
- Regroup
    - ![image](https://gyazo.com/2441807c2369e1554dd2c0c4a463836c/thumb/1000)
    - ![image](https://gyazo.com/29ac8099d8e59321c5ec9a2608d5d8be/thumb/1000)
        - Oh, right, you're not leaving the border, you're leaving the background.
    - So it's like this.
        - ![image](https://gyazo.com/19496a64d88a4040247134174fc7f9cb/thumb/1000)
        - This would make it irrelevant if there is a border or not.

This development is more secure when refactoring because I'm using Cypress to check the state I want to check, check the screen, see it's what I expect, and then change the code to check it...and so on. But I still haven't added event handlers or anything for human manipulation. Is this okay?
- From the viewpoint of "we should make something that users can actually use and have them use it and observe it as soon as possible," is that a long way off?


Write down the functionality needed to make it actually usable.
    - [[MovideaFunctionality required to make it actually usable]]

I was going to put off the issue of offset shifting when moving a child element, but I thought I'd put it off.
I thought it would be better to write the test in a simple state, so we'll do that first thing tomorrow.
If you want to change the way you do something later, it should be easier to do it if you have a test.

---
This page is auto-translated from [/nishio/2021-07-13Movidea開発日記](https://scrapbox.io/nishio/2021-07-13Movidea開発日記) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.