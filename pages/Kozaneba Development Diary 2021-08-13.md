---
title: "Kozaneba Development Diary 2021-08-13"
---

prev  [[Kozaneba Development Diary 2021-08-12]]

![image](https://gyazo.com/93b73c4eaa1835eaf6d5e8436715f996/thumb/1000)
Opening and closing the group, done!
Now, though, the default title is the one that combines the contents,
If we add an "Edit Title" menu item here...

Edit Title" and "Re-edit Kozane" are dialogically similar to "Add Kozane," but I feel like putting these together is a bad abstraction, so I'll just copy and paste and add more.

edit title
![image](https://gyazo.com/797258ee27a16538348df8e600986327/thumb/1000)

split
![image](https://gyazo.com/13893c87a8d7baa73a5bb505d7b5d43b/thumb/1000)

TODO:
- add tests for new features
- add tutorial pages for new features

![image](https://gyazo.com/46f848bff5842f5715d76e8f01a5bf64/thumb/1000)

This week's summary
- Tutorial Creation
- user test
- Screen recording of the work process with Regroup, with audio commentary (first half)
- Opening and Closing Groups
- Edit Group Title
- division of a small piece of land
- Fixed a bug in the position and dragging of the closed kneecap
- Bug: Clicking on a kozane in a group brings up the group's menu.
    - Bug when deleting a kozane in a group
        - Correction ✅


Future Flow
- User testing is overflowing my capacity, so the pace is slow.
- First, implement the functionality you need for your own use, and then cover it with proper automated tests before including it in the tutorial.
- Once that's all done, we'll make the tutorials multilingual and create a user forum.
- Long-term goal is user scalability

I also made the second half of the commentary video.
    - [[Regroup screen recording explanation]]

I've been a little slammed with deadlines, so next week I'll sit back, clean up the code, cover it with tests, and add explanations to the tutorials.
- There is no tutorial on how to view saved pages.
- It is not good because the added stickies are placed at the origin in the world coordinates, so put them in the center of the screen.
- Big deal: I knew going the route of using the drag-drop API was not a good idea (looks very environment-dependent).
- The test itself has been created by trial and error and patchwork, so it's chaotic.
- I want to make a user page.
    - Need a list of places used in the past
    - Placement of future expansion, etc.
- I'd like to make a "of course you can use Scrapbox cards as small bills because it's DOM" video as a catchy teaser at the right time.



---
This page is auto-translated from [/nishio/Kozaneba開発日記2021-08-13](https://scrapbox.io/nishio/Kozaneba開発日記2021-08-13) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.