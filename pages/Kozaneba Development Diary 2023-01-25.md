---
title: "Kozaneba Development Diary 2023-01-25"
---

It has been a long time since the title "Kozaneba Development Diary
- I was going to post a link to ~ before, but it looks like it would be better to make a page summarizing June-July activities instead of an individual day, so I'll do that later.

Summary of recent activities
    - [[Create a development environment for Kozaneba]] 2023-01-11
    - [[Resolution: Uncaught TypeError: use_force_update_1.default is not a function]]
- [/kozaneba-forum-jp/solutions:Crash when creating a non-existent Scrapbox page kozane](https://scrapbox.io/kozaneba-forum-jp/solutions:Crash when creating a non-existent Scrapbox page kozane).


- [[Line drawing UI]]
- I use Kozaneba for fireworks to think about and am not happy with the current ability to draw lines
    - The current implementation is the reason that "it must be possible to describe the relationship between three or more things in a way other than putting them in a group."
    - However, "for the majority of use cases, two relationships are sufficient," so we want to focus on this and make it easier to use.

What do you need to do?
- Bring up the "Draw a line" menu when clicking on a kozane or group.
- Drag or click it to enter "temporary line drawing mode".
- Draw a line in the sand with a close-up on another element.
Can you do that?
- Can you enter the mode by clicking on the menu?
- Where is the current mode managed?
- If "Start Line Drawing Mode" is selected in the menu, subsequent mouse events must not be processed normally
- There's another problem with giving a preview of the line in the middle.

implementation-wise.
- Mouse events are handled differently depending on the implicit mode.
- What this mode represents is this
ts

```typescript
type TDragTarget = "" | "selection" | TItemId;
type TMouseState = "" | "selecting" | "middle_dragging";
```

- So, add a "line drawing mode" to TMouseState.
    - Added a menu that goes into the context menu when clicking on a kozane or group
    - Added processing in various event handlers when in this mode
        - Kozane or up on a group to "create a line and get out of the mode."
        - Up on the canvas to "stop drawing lines" (exit from the mode without creating a line).

If the preview display during drawing is ignored, "the ability to easily draw lines between elements" itself could be added quickly.
- It means about one day tomorrow.

Preview display during drawing
- This is better to have, but tricky for two reasons
    - Currently "line" is defined as "something that connects multiple elements".
        - Since the "line of writing" is not connected to an element, you can either create a virtual element that follows the mouse pointer, or you can change the definition of the line.
    - Worried about performance issues when updating React State since the value is updated by mouse move.

Either create a "preview of the line to be written" entity separate from the existing line
- 0 to 1 present
- Allow both elements and coordinates to be taken as endpoints
    - Q: Why can't it simply be coordinates?
        - A: Because elements have sizes and lines are not drawn from the center!
- If you keep this as a separate component from the rest of the "whole line," the performance problem is not as severe because the whole redraw is not running.

Once this is done, the next step is to
- Problem with subtle deletion of lines.
- The line "fades with distance" can be turned off as an option.
- Shorten access to functions that are frequently used in doing Thinking Fireworks.
    - For example, "Draw a line and add a kozane" should be one menu item.
    - There's a good chance there's a keyboard in the situation, so a hotkey on the menu would be a good idea.
    - Hotkey Add Kozane Dialog

Low priority ideas
- Ability to turn off "automatic font sizing and wrapping
    - Change place defaults
    - Change by Kozane unit
    - why？
        - As an exploration of the question of how a group title should be, it would be a good idea to have a group title-like horizontal kozane that does not wrap around in the first place, so that trial and error can be used.
        - When trying to analyze source code elements, it doesn't feel right for identifiers to wrap around.
            - The idiosyncrasies that tend to make global things have longer names are reversed with natural language.
            - In natural language, the more you use something here and there, the shorter it gets.
        - I think it's good for expressing relationships between elements in lines, organizing thoughts as you move them around, and for verbalizing the structure of source code...


---
2023-01-26

Kozane doesn't have an up handler to begin with.
- Because unlike the group, Kozane doesn't accept drag-drops.
- Can I handle this in DOWN?
    - No. Is this the initiation of drugs?
- So the canvas and the group are receiving the up and deciding if it's a click or not.

You must record the object when you start drawing the line.

It's done.
- ![image](https://gyazo.com/e44cf7072cf0593f8c4c5a228e264dcb/thumb/1000)
- I was thinking of adding a "Show lines as they are drawn" feature, but I wanted to be able to specify whether they are arrows or lines first.


Open AddKozane Dialog with Enter key
- It's tricky to put hotkeys on menus.
- It needs to be switched on whether the menu is visible or not.


Image Preparation
- Line Arrow Conflict Equal
- ![image](https://gyazo.com/53344a6db2cdf1c7ade0a2dd377c4793/thumb/1000)![image](https://gyazo.com/53c370b43e1328439164baaed41be7a2/thumb/1000)![image](https://gyazo.com/c6611e172ffb5f19558aa796d31b4fe7/thumb/1000)![image](https://gyazo.com/002bd9eca37cd538f35d369ed01b2659/thumb/1000)
- ![image](https://gyazo.com/6453798d8fce56f10763d0e0f9d6c1b5/thumb/1000)

It's done.
![image](https://gyazo.com/2f0c666d1a8f3bbee59f0868ccf524c0/thumb/1000)

Preview function, do we really need it?
- Don't we need to improve the method of removing lines more than that?
- If you press the menu item "leave from lines", which is not easy to understand, the kozane will leave from all lines.
    - = If there is only a binary relationship, it is equivalent to "erasing all connected lines".
- How about erasing it with this UI we made this time.
    - You can specify two elements, so "erase the line between the two elements".
- It's done.
    - ![image](https://gyazo.com/f31c63af7bb9bba26c8db29d95493b0d/thumb/1000)


next action thinking

I'm thinking at this moment "click and use the A key to create a kozane with a line from it and go into edit mode", but I'll cool down a bit and think about whether that's really the right thing to do.

Hotkeys on menus is another story.
- It's unknown if you'll be using that feature often.
- We should put it on the menu as an experimental feature, use it for a while, and then think about it.
    - No, no, no, I was going to add this quick and easy, but it's not easy at all.
    - After a user's asynchronous "add Kozane", there is no hook point for the added items.
        - I think it would be beneficial for future expansion if there were...
    - If this function is used
        - Click, click menu, enter text, move to desired location
    - If not used
        - Enter, enter text, click, click menu, click, go where you want
    - It's not as much work as it sounds.

It is more important to add a rendering method that does not automatically adjust fonts
- This is a big task because it also changes the form of data storage
- It would be a good idea to implement this as an experimental feature that will not be saved once it is implemented.

The ability to turn off line translucency is just a visual option, so let's put it on as an experimental feature, this is easy
- I thought I didn't need a UI.
- Exposed ✅feature chart toggle

I also had to rebuild the Cypress test environment.

next action:
- Cypress Testing Environment
- Experimentation with rendering methods without automatic font adjustment

2023-01-27
- [[Cypess 12]]
    - [[(Resolved)Cannot find type definition file for ~]]

from  [[Kozaneba Development Diary 2021-08-03]]
- > I found that in Cypress environment, Google says "This browser is insecure and will not allow you to log in".
- Using [Firebase Local Emulator

[https://firebase.google.com/docs/emulator-suite/install_and_configure?hl=ja](https://firebase.google.com/docs/emulator-suite/install_and_configure?hl=ja)
- [https://firebase.google.com/docs/cli?hl=ja](https://firebase.google.com/docs/cli?hl=ja)
    - `$ npm install -g firebase-tools`
    - `$ firebase login`
- `$ firebase init emulators `
- `$ firebase emulators:start --import firebase_emulator_data`
    - `Error: Process `java -version` has exited with code 1. Please make sure Java is installed and on your system PATH.`
    - `Error: firebase-tools no longer supports Java version before 11. Please upgrade to Java version 11 or above to continue using the emulators.`
It's done.

I was going to test the display changes, just rewriting the constants via API, but it's in the form of constant styles based on the constants to begin with, so it doesn't make sense to rewrite the constants later via API.
- If the style is going to refer to a constant every time, that's going to be a performance issue.
- Proposal to add no_fontsize_adjustment to TKozaneItem's custom
    - Switching the entire DOM

---
This page is auto-translated from [/nishio/Kozaneba開発日記2023-01-25](https://scrapbox.io/nishio/Kozaneba開発日記2023-01-25) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.