---
title: "pMovidea"
---

This is the hub page for personal notes for the [[Regroup]] reimplementation project

    - [[2021-07-20Movidea Development Diary]]
    - [[2021-07-26Movidea Development Diary]]
    - [[2021-07-27Movidea Development Diary]]
    - [[2021-07-28Movidea Development Diary]]
    - [[2021-07-29Movidea Development Diary]]

branding
- The most core function is "to move and organize fragments of thoughts", so I brought "moveable".
- Short form movidea

Why reimplement?
- Trial and error results in code complexity, which is an obstacle to adding new features.
- After reading [/shokai/Scrapbox development process](https://scrapbox.io/shokai/Scrapbox development process), I thought the following ideas were important
    - Focus on Impact
    - I can't get close to "something that looks like it belongs somewhere."
    - Don't add features unnecessarily
    - I won't let it bug you.
    - Increasing the amount of code gets in the way of prototyping the next feature.
- Minimal functionality with minimal code

Not to do
- No Canvas
    - Free handwritten additions are not implemented.
    - Not implementing lasso selection.
    - why?
        - When we created Regroup, the first thing we tested was whether it was possible to smoothly add handwriting, assuming an iPad + Apple Pencil.
        - We found out to what extent it was technically possible (quite possible), but not so much in terms of user needs.
        - The realization of this is generating strong technical constraints, so it is better to seal it once and find another way to do it.

To do
- testing a microphone
- Using [styled-components
    - Last time it was Canvas, so it was defined in JS as far as style was concerned.
    - This time we'll use the DOM, but it's not nice to separate it into CSS.
- [[ReactN]] + [[immer]]
    - Last time I made it while learning React, I started making it using the built-in useState system.
        - But since it's "an app that puts stickies on a giant whiteboard", the parent App component will have most of the state
        - I learned later that [[ReactN]] was better suited for my purposes.

What's Next
- Previous [[2021-07-20Movidea Development Diary]] Previous [[2021-07-19Movidea Development Diary]].
- Cover the verification of the mistake with a test case before implementing the selection move.



Verification.
- Can you make stickies without Canvas?
    - Important technical points
            - [[✅ Can the font size be adjusted automatically?]]
        - Dragging, well, you can do that.
            - I'm concerned about interference with text selection.
            - Last time I made an experimental sample with hard code, but later I started to use that after [[JSON import function]] was created, this time I will make it first and make it a test case
                - Include a version string in the data.
            - 1: Make the exported JSON from the current Regroup readable
                - The question of whether the data structure should remain the same as before is not considered now.
                - ✅ [[2021-07-14Movidea Development Diary]]
            - 2: Use it to create test cases
            - 3: Data structure changes are easier to make if covered by testing.
            - →First, [Expose ReactN and use it from Cypress.

- Can you zoom in and out smoothly?
        - [[✅Smooth scaling and translating in the DOM]]
        - [[Macbook trackpad for scaling and parallel movement]]

- I want to cover the data storage format with thorough testing, since it is hard to notice bugs or lost data when they occur.
    - You can't protect them with a mold.

Last time I made it without testing and started testing with jest-electron in the middle of the process.
- It was difficult to make it testable because it was not designed with testing in mind and it was full of asynchronous processing.
- It ended up not being covered in the test.
- This time [[Expose ReactN and use it from Cypress.]].

Last time it was iPad + Apple Pencil assumption, this time it is MacBook assumption.

Last time, the world coordinate system of the sticky was tightly coupled with that of the device, but I think it's better to separate them.

Group Structure
- Pointer to child element
- Drawing order?
- doorplate
    - This is not a pointer.
    - Not even a child element.
    - Can it be a child element?
        - You shouldn't.
    - Mere text?
        - You can renew as many times as you like.
        - In the menu like edit title
        - So you should know that this is not your average sticky note.
        - What to do when it opens
            - It used to be a nameplate sticky, but not this one.
        - Wouldn't it be nice if it showed up as a "group title?"
            - ✅ [[2021-07-13Movidea Development Diary]]
            - ![image](https://gyazo.com/b181a51e078ac34a54860bed29bc2bf7/thumb/1000)
        - What should happen when you dismantle 🤔 this
            - If you don't have a title, just demolish it as is.
            - When there is a title, it is an intellectual product and should not be lost
                - Do you want to make it a sticky note?
                - 🤔When you group it back together again?
                - How about just selecting stickies and copying and pasting them without making an elaborate UI?
    - [Folded things get one step bigger.
    - [[What should happen when a compressed sticky is decompressed?]]
    - Last time I closed it with a menu from open, and opened it with one click from closed.
    - Let's try to toggle between "default open" and "default close."
        - Distinguish by borders?










- [[What should the editorial URL be?]]

consideration
    - [[Regroup to Movidea]]

done

✅Use normal menu [[2021-07-15Movidea Development Diary#60eff1fcaff09e0000c6d303]].
- context menu
    - Last time I set it to [[Balloon Menu]].
        - Is this appropriate?
        - The menu wording is written horizontally, so the buttons are too long and narrow to be placed side by side
        - It's better to have a vertically aligned menu like the old context menu.

---
This page is auto-translated from [/nishio/pMovidea](https://scrapbox.io/nishio/pMovidea) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.