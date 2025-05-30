---
title: "Line drawing UI"
---

How to achieve the use case of drawing a line between two elements and wanting the elements to stay connected even if they are moved.
- Thinking about improving Kozaneba's line drawing UI
- Putting aside for a moment the convenience of internal design, consider what a "line-drawing UI" might look like

Mounting Method 1:.
- Introduce a line-drawing mode
- Clicking on element A and element B draws a line.

Mounting Method 2:.
- Introduce a line-drawing mode
- Pointer down on element A, pointer up on element B to draw a line.

Implementation Method 3:.
- Select multiple elements
    - A context menu appears.
- Select "Draw a line" from the menu.

Implementation Method 4: The
- In the menu of globals, "Add Line."
- A line with null ends is formed.
- Drag and drop it to element A and element B to connect them.

Implementation Method 5: The
- Clicking on element A causes a handle to appear.
- Drag-drop a handle onto element B to draw a line.

About Line Drawing Mode
- If you want to draw a line all together, it's easy to enter the mode.
- If you have to draw a line and move an element frequently, you need to switch modes every time you draw a line and move an element.
    - We need to know which mode we are in.
    - People will draw lines trying to move elements.
- Google Slide is an implementation method 2
    - Drag-drop targets handles, not the elements themselves

Mounting method 3
- Current Kozaneba implementation
- The advantage is that the expression is not limited to the relationship between two elements.
- If you draw the line at something close, it's acceptable.
- When trying to draw a line on a distant object or in an intricate arrangement, "select a range" will involve other objects.
    - operational workarounds
        - Move the target element closer
        - draw a line
        - Put it back in its original place.
    - This is troublesome!
    - As I was creating and using the line functions, I realized that these situations were more frequent and troublesome than I had expected.
        - I've come to believe that the disadvantages outweigh the advantages of multiplying polynomial relationships.

Mounting method 4
- Keynote adds a line when the line button is pressed.
    - No connection to the elements?
- Google Slide also does this when you click on it in "draw a line mode".
- If you define a line as "a line is something that connects elements" because it temporarily creates a "line that leads nowhere", problems arise.
    - Care should be taken when designing

Mounting method 5
- Miro Implementation
    - The current Kozaneba is also the same in that when you click on an element, a context menu appears, so you are "in temporary mode".
        - I can get the handle out.
        - The "temporary menuing mode" must switch to "temporary line drawing mode" when the pointer is down on the handle.


relevance
- Can the line be selected?
    - If a line has a hit judgment, the line will take an event when you try to move the element.
- How to erase lines

---
This page is auto-translated from [/nishio/線を引くUI](https://scrapbox.io/nishio/線を引くUI) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.