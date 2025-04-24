---
title: "Kozaneba Development Diary 2021-12-22"
---

I used Kozaneba for various demands for a while.
    - [[Keichobot presentation ready December 2021]]
        - [[Kozaneba:I want to put Keichobot in context.]]
    - [[Kozaneba:Experiential Processes and the Creation of Meaning]]
- Based on these two presentations, I thought [[Tools to assist in understanding difficult books]] would be a good first step to try using Kozaneba. It was decided that
- So I tried to use it for that purpose.
        - [[Kozaneba:On the phenomenology of language]]
    - [[Kozaneba:dwell-think]]
        - [[Kozaneba: The Formation of Chinese Hua Yan through the Fusion of the Hua Yan Sutra and Zhuangzi]]


Problem of heavier weight in larger quantities.
- In the first place, it is beyond human capacity to add more in that state, so we should move on to the phase of output in our own words.
    - [[Scrapbox-like recall effect on Kozaneba]]

- [[Kozaneba Development Diary 2021-11-26]]
- [[Kozaneba Development Diary 2021-12-10]]

Group disappearance problem under high load
- When dragging a group from a selected state, the first cause is that the deselection redraw runs after the start of the drag.
- This bug breaks the "What is being dragged is not a drop target" and causes "X is dropped on X at the top level, so X is removed from the top level drawing list and X is added to X's children", which causes it to disappear from the screen.

release notes
- Fixed a bug that caused a group to be hidden when dragging on a group outside of the selection while there is a selection
- Dragging outside of a selection with a selection now simply deselects the selection.
- Selection is now automatically deselected if there is nothing to select in the selected area.

Make long binary relationships translucent

![image](https://gyazo.com/332d57d2df82a9b54635aec15209cc32/thumb/1000)

![image](https://gyazo.com/5d6b761b9da4518ff40c5f51ce4262f3/thumb/1000)
![image](https://gyazo.com/3d188c2e0df12805a388e79ea83e53e1/thumb/1000)
![image](https://gyazo.com/e45792a1cccb534549a0386a44a8f7df/thumb/1000)
![image](https://gyazo.com/496f0f14cb1678b80d148f3be5fc36c7/thumb/1000)![image](https://gyazo.com/9cefcf1c5d31a7486b3e055cd58b1d6e/thumb/1000)
![image](https://gyazo.com/4245a9bdefacdd730a79773f2bf52283/thumb/1000)
![image](https://gyazo.com/ee21d37883a766abeb4ef519ee9f5984/thumb/1000)
![image](https://gyazo.com/5383a098af350bf3ec1727fa19190b8f/thumb/1000)

Ah, I see.

And I found a way to break it even harder.
- ![image](https://gyazo.com/1019c8972558303dcb03d5ded37af1a4/thumb/1000)

The first part of the problem is that the thickness of the border itself and the height of the header are not taken into account when calculating the intersection of the line and the border.
As for the latter part, when the position of a kozane in a nested group is updated, some value of the parent's parent's group is not updated.
I've been thinking that Kozane's jumps occur when structuring complex sentences this time, but perhaps this update omission is the cause.

Fix the latter first because the scope of impact and problems are greater.
As for the former, it's strange that the line drawing code needs to know the height of the group's header in the first place, so why not get the boundary box and calculate from there?

[[2021-12-23]]
- [[Organize in reverse chronological order]]
- I hadn't yet deployed the functionality to make the lines translucent that I put in on Wednesday.
    - I've found this to be very beneficial.
    - You won't have to think, "I can't read this line because it's over the one below me, so I'll move it."
- Everything is connected, and this still preserves the relationship "in proximity in the original sentence" = [Existing Structure
    - Now that we have this situation backed up, we can "reach the new structure without painful jumps" if we do "not need to keep the original structure" = "move away from it, destroying the original structure so that the arrows connecting it are in close proximity".
    - I wonder if this could be mechanically assisted... i.e. if the proximity is a weak spring, the arrow is a strong spring, and the physics is applied so that the arrow is the right length...
- I want "Rotate Selection 90 Degrees."

next  [[Kozaneba Development Diary 2021-12-27]]

---
This page is auto-translated from [/nishio/Kozaneba開発日記2021-12-22](https://scrapbox.io/nishio/Kozaneba開発日記2021-12-22) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.