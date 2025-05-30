---
title: "Kozaneba Development Diary 2021-08-20"
---

prev  [[Kozaneba Development Diary 2021-08-19]]

- Tutorial Updates
- read-only sharing
- Wheel sensitivity adjustment (a step toward expandability by the user)

Even at this stage, collaborative editing is possible by sharing URLs, but I don't dare write about situations where multiple people share and use them in the help section.

As for extensibility by the user
- It is easy for users to start with the look and feel
    - But now there's no lead-only sharing, so there's no way to show others what you've made (and guarantee it won't be destroyed).
- Easy to implement UI system setting changes and menu additions
    - but I can't think of anything I'd want to do with that unless you're using the tool.
The first priority is lead-only sharing, since the state of the
- I can show you what I'm using as an actual demo.

I'm too good at Japanese.
- > Temporary invisibility of items that are not important and therefore do not need to be on the screen, but are not important enough to delete.

You can close the group. You can temporarily make invisible those that are not important and therefore do not need to be on the screen, but are not important enough to be deleted.

You can put a nameplate on the closed group. If there is no name tag, all contents will be displayed.

In the process of organizing your thoughts, you often find things that are not very important. They do not need to be on the screen, but you do not want to delete them because you may use them later. You can temporarily make these things invisible.

You can close the group.
In the process of organizing your thoughts, you will often find things that are not so important. They don't need to be on the screen, but you don't want to delete them because you might use them later. You can make such things temporarily invisible.

You can put a nameplate on the closed group. If there is no name tag, all contents will be displayed.

Features I want
- I want copy and paste.

I'm afraid the hot keys work to handle the feedback screen.
- Correction ✅

This week's summary
- Drag operation was realized by DragDropAPI of browser, but changed to MouseUp/Move/Down because of the problem of different behavior by browsers.
- Keyboard controls are available for those without touchpads or wheels. Hotkeys are attached to frequently used operations.
- Select a range of text and copy text (2D layouts are converted to one-dimensional, and group inclusions are expressed by indentation, so they can be pasted directly into Scrapbox, etc.).
- Help function, Table of Contents
- Ba with editing rights can be listed in the user dialog.
- Create Japanese and English forums
- Update the tutorial in light of these features

Future Flow
- Tutorial tests updated to match new tutorials
    - The movement by the cursor was immediately regre...
- I will use it and find the lack of testing I will implement mainly the features that I "wanted to use and wanted, and that were in Regroup but lacking here".
    - Copy, paste, read-only sharing
- User expandability is experimentally tested by changing wheel sensitivity, etc.

![image](https://gyazo.com/18d8cd914bc2004ec54ffaef203cbc19/thumb/1000)


> User extensibility is wheel sensitivity change
- [/kozaneba-forum-jp/some constants can be changed by users](https://scrapbox.io/kozaneba-forum-jp/some constants can be changed by users)✅.
- Now that we can rewrite it from the developer console and test the behavior, the next step is the ability to create a "script that runs on load".


[/kozaneba-forum-jp/ Once you have completed the tutorial, do not restart it](https://scrapbox.io/kozaneba-forum-jp/ Once you have completed the tutorial, do not restart it).
- I thought about not showing it if the user is already logged in, but this decision is asynchronous, so it's no good.
- Create `/#home` or `/#new`?
- It should work the same way as user scripts.
- Rather, it would be better to use `kozaneba.constants.skip_tutorial = true` in the user script.

---
This page is auto-translated from [/nishio/Kozaneba開発日記2021-08-20](https://scrapbox.io/nishio/Kozaneba開発日記2021-08-20) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.