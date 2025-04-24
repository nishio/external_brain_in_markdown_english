---
title: "Kozaneba Development Diary 2022-06-08"
---

- Fixed a bug that the drawing position of arrows in a group was misaligned.
    - Did the last fix enbuggle it?
    - Create test cases
- Add an indication of the number of kozane sheets and rendering time

### 11:00
- <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>🍅11:56-12:21 make test cases.
    - A reproducible test case was created.
    - When a group is dragged, the bounding box is not updated, but the start and end points of the line segments are updated and the calculated intersection is shifted.
    - Huh? Why did it work before? Didn't it ever work before?
        - I've tried to checkout the previous version, but I can't reproduce the bug.
### 12:00
- <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Okay, the argument I originally passed to the intersection calculation function was wrong, and if you were in a group, you were out of alignment, but the old algorithm was "assume the starting point is out of the center of the box and calculate the intersection by focusing only on the slope", so it wasn't discovered.
### 15:00
- <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>🍅15:44-16:09 continued.
    - fixed, released✅
### 16:00
- <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>🍅16:42-17:07 Show number of sheets and rendering time.
    - For now, let's skip the UI and just generate a function to display in the window.
    - Turns out there are a little over 500 things to display.
        - ![image](https://gyazo.com/058df9a1617de0a233372cf88fd8e9bf/thumb/1000)

    - Counting is easy, but I'm not quite sure where to measure time...
### 17:00
- <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Hmmm, I was going to measure the time taken to process the onWheel, but this only updates the React state, and the event handler itself finishes quickly.
    - I wonder if the movement will be smoother if we do our own state management instead of leaving it to React?
    - The reason I'm not doing that now is because the wheel event doesn't have an event to indicate "end" unlike mouse dragging and the like.
### 21:00
- <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>In onWheel, it only calls ReactN's GlobalStateManager.set, but that takes up 3.7 msec of the 16.7 msec per frame. This is about the only thing that can be cut.
    - ![image](https://gyazo.com/fd71b77d7336cf48b428455f2de706dd/thumb/1000)
    - I guess I still have to do the status updates and screen updates on my own without going through React?
    - When it's running smoothly, it's about 2 msec.
    - ![image](https://gyazo.com/f9c8702102b8446c4cd9954c783a5910/thumb/1000)
    - Hmmm, this is mainly due to the fact that Paint (and the same amount of time of unknown content) is growing, so cutting out status updates won't help. It's like, "If you want a solution, get a new MacBook."
### 23:00
- <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I was curious to find out what this shaded line in the CPU tab was, and found out that it was "processing other than the main thread".
    - ![image](https://gyazo.com/9f31f26cf2c03f4aa14b0a5460151fb3/thumb/1000)
    - What is so full of processing other than the main thread?
    - Are you saying that React is doing state management outside of the main thread?
        - How is that possible...?
    - If you select a zone with only projectile lines, the summary view is Idle, but in reality it is a Dropped Frame because it was not processed in time.
        - ![image](https://gyazo.com/b4908a7993bd1b884d284c98dcab4660/thumb/1000)
        - The call tree and other displays are all empty, perhaps only the main thread process is gathering information.

consideration
- I have about 600 Kozane out there, which I think is rare for a user.
    - It's taking time outside the main thread, so maybe trying hard to improve the process implemented in the script won't solve the problem.
    - Rather, let's not try so hard and thwart the event.
        - [https://developer.mozilla.org/ja/docs/Web/API/Element/scroll_event](https://developer.mozilla.org/ja/docs/Web/API/Element/scroll_event)

Current [Fixed size group titles are unreadable when zoomed out
![image](https://gyazo.com/3f6ab3b2f2a355bf7ea328b25b7b12fd/thumb/1000)
I think some sort of algorithm should be used to increase the font size of the title.
- It's going to be buggy when something that used to be a fixed size becomes variable~~~.
- I'll set a maximum font size, and if it goes over the length, I'll shrink it, I guess.

- About [Petit hang on load
- Asynchronous font size calculation?
- If you make it asynchronous, well, it's displayed in "small print" for about the same amount of time as if it's petit-hung.
- I would prefer to store the calculated values on the server...
    - If it's "recalculate if not," I can read past data with no problem.

What should happen to link notation when copying and pasting from Scrapbox?
- If it is in Scrapbox mode, you can parse it as Scrapbox.
- Should it be a Kozane or a Scrapbox card?
- [/villagepump/Kozaneba+Scrapbox](https://scrapbox.io/villagepump/Kozaneba+Scrapbox)
- It looks good to be a kozane and be able to expand from there.

---
This page is auto-translated from [/nishio/Kozaneba開発日記2022-06-08](https://scrapbox.io/nishio/Kozaneba開発日記2022-06-08) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.