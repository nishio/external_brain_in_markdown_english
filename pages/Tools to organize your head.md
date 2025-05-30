---
title: "Tools to organize your head"
---

This project has been replaced by [Kozaneba digital stationery to organize your thoughts
We have kept the past pages for your reference.
---
![image](https://gyazo.com/dd8d0582be11327f3f6da943774122ac/thumb/1000)
- [[The Intellectual Production of Engineers]] introduced the [[KJ method]] using small sticky notes alone as a solution to a situation where there is too much information and one's mind is not organized.
The author himself uses this method for writing "Technology Supporting Coding" and "Intellectual Production Techniques for Engineers," as well as for preparing various lecture materials, and has found it to be effective. On the other hand, there is an inconvenience of using paper, and I am wondering if it is possible to solve this problem electronically.

Prototype currently under development
- Development code name: [[Regroup]]
- Assumed main use
    - Create batch stickies from text data
        - It is assumed that there are at least 50 sticky notes with information.
        - Although the write-from-scratch method itself can be done with this tool, it would be smoother to write it out in a text editor, paper notepad, chat or groupware before putting it into this tool.
            - Example: take a walk while thinking, write down what comes to mind in a notepad on your phone, import it into Regroup when you get home, and organize it.
            - Example: We discussed a certain topic in chat or groupware. I felt this content was useful -> Import and organize chat logs
                - With this use case, often in a state of "I had a blind spot in what I was thinking at the beginning of the conversation, and through the conversation I realized a new perspective," there is a great deal of learning in the process of rearranging past statements from a new perspective
    - Move stickies on the screen to collect "possibly related items" nearby.
        - We believe that "why is there a relationship?" and "what kind of relationship?" are not verbalized at first, but are verbalized in the process of collecting. Therefore, it is necessary to be able to organize using "positional proximity" in a non-verbalized state.
    - Utilize zooming in and out of the screen
        - The display surface of electronic devices is too narrow compared to the ideal work area size. Therefore, it is important to be able to smoothly zoom in and out of the screen. Repeatedly display the entire image and zoom in on the area of interest.
        - Zooming in and out of the screen is primarily intended to be done by pinch gesture on an iPad, but it can also work on a PC for those who do not have an iPad. Use on smartphones with small screen sizes is deprecated.

- How to operate
    - Create New
        - [https://regroup.netlify.app/#/blank](https://regroup.netlify.app/#/blank)
        - A blank sheet of paper opens at this link.
        - This is a mode that is not automatically saved
        - ![image](https://gyazo.com/b7eeffd4c7964248cbe779c0077640a1/thumb/1000)
        - NET NC in the toolbar means "not connected".
        - Various functions can be used from the menu of three dots of buttons next to it.
        - Selecting "Save as New Map" saves the map to the cloud and automatically saves it from then on.
            - Pages with URLs like `https://regroup.netlify.app/#/key=AWsx0mgzjbzugTrCIjCo` open in a separate tab.
                - Press the "Open URL" button in Safari on the iPad, as it is blocked by the pop-up blocker and will not open automatically.
            - This URL is a set of editing permissions, so if you open this URL on a PC and an iPad, for example, you can edit it on either.
            - Edits made on one side are automatically reflected on the other.
        - There is no "list of maps I made" screen, so you can bookmark it at this point.

    - Importing Stickies
        - Menu→Import Multi-line text to bring up a dialog for importing text.
            - Each line will be one sticky note, so it should be chopped to a reasonable length.
            - In the example below, a document of about 180 characters is pasted and then finely chopped.
                - This is for illustrative purposes only, and since there are 16 sheets, the number of sheets is considerably less than the intended use.
                - ![image](https://gyazo.com/8afe018e1ba63ccf81a496553185de5e/thumb/1000)
        - Press the Import button to turn it into a sticky note.
            - ![image](https://gyazo.com/1ecfb0dd08a1a9b550afb7ac4cc162fc/thumb/1000)
    - Moving stickies
        - Initially, it is in "sticky-move mode".
            - ![image](https://gyazo.com/4ca9ec9c8ef1bed3c8b42bdf06683d58/thumb/1000)
            - On a PC, you can drag with the mouse, and on an iPad, you can drag with your finger.
            - When using the Apple Pencil on the iPad, the specification is to write by hand, not move
        - In lasso mode next to the
            - Multiple pieces can be enclosed and moved together.
            - Drag a single sticky to move it by itself.
        - Example of move result
            - ![image](https://gyazo.com/ba20e590221d43f2d6879a3002d06a3b/thumb/1000)

    - Zoom in/out
        - On the iPad, the two-finger touch and shrink/expand operation (pinch in/pinch out) should work as you imagine.
        - On PC
            - A MacBook touchpad can do the same with a pinch operation.
            - In other environments, if you have a wheel mouse, you can do it with the wheel.
            - This is OK in environments where two-finger up/down gestures on the touchpad are interpreted as wheel operation.
            - For environments where none of the above is available, you can hold down the shift key and drag up and down, but only as a last resort.
        - In the case of a pinch, the movement combines parallelism and scaling appropriately based on the position before and after the finger movement
        - In the case of a wheel, etc., the current mouse position is used as the center for zooming in and out. Move the mouse to the location you want to focus on and then zoom in.
        - In this example, the sticky note documents are short and few in number, so it is difficult to see the need for zooming.
            - When used in a realistic situation where you want to "organize your head", the original size will not fit on the screen, and if you zoom out to where it fits on the screen, you will not be able to see the fine print on each sticky.
            - So it is necessary to repeat zooming in and out, and it is essential that this function be readily available.
            - Example
                - ![image](https://gyazo.com/6e74f6a43a52c9a6f66fae675a08194f/thumb/1000)
                    - from  [[0 to 1 capability" and "team-building capability."]]
                    - I use the grouping and handwritten additions described below.
            - Using "Make stickies bigger" (described below), you can create a table-top sticky that is visible even when zoomed out.

    - Minimum functionality required so far.
        - We've implemented and experimented with many other features, but it's not essential to understand and use those features.

    - grouping
        - Stickies can be enclosed and "grouped" with the lasso tool
            - ![image](https://gyazo.com/d53403c24ec1ecc953e83b23875712cc/thumb/1000)
            - This group can be moved together
                - When you're moving multiple stickies around, looking for the right placement, you can treat them as one lump without having to lasso them every time.
        - Groups can be opened and closed
            - ![image](https://gyazo.com/784ac36ddd08c3456fd3808e2f0081a9/thumb/1000)

            - When closed (folded), it becomes the size of a sheet of sticky notes.
            - Closed stickies can be opened with one click.
            - When folded, the sticky in the top left most corner is displayed.
            - Folding groups, especially when there are too many stickies, allows you to ignore the branches and focus on the higher level structure.
            - For those familiar with the KJ method, it is the equivalent of "bundling cards.
                - If you are doing the KJ method on paper, once you bundle the paper, it can be a hassle to open it again to check the inside, or the spatial arrangement before bundling can be lost. This is what we wanted to solve.
                - On the other hand, if there are 50 or so sticky notes, they can often be organized without bundling them, making it difficult to explain the need for them.

    - handwritten addition
        - Example
            - ![image](https://gyazo.com/dd8d0582be11327f3f6da943774122ac/thumb/1000)
        - Especially if you're using the Apple Pencil, you can easily add to your handwriting.
            - Even in move mode, the Apple Pencil can be used for handwriting, so you can draw with the pencil and move it with your finger.
        - A "pen input mode" is available for PCs.
            - ![image](https://gyazo.com/b30dacc57ca922ec09f6a8fe4aeaf0a6/thumb/1000)
            - In this mode, mouse operations are treated as pen input, but drawing lines with the mouse is not recommended.
        - Mainly sticky notes, with some additions and illustrations of things that are difficult to express in writing are assumed to be used.
            - Handwritten note-taking of a one-hour lecture can become too heavy with too much handwriting on the screen or too much data and fail to save to the cloud.

    - Sharing and co-editing with permalinks
        - Just share the URL of the editing screen for collaborative editing.
            - If you use a Mac, the [[Handoff]] feature makes it easy to open the same page on multiple devices.
        - This is a feature designed for multiple devices by a single person
            - When multiple people edit at the same time, one edit is overwritten by the other depending on the timing.
            - For example, when multiple people are editing while sharing in a videoconference, it is necessary to say, "I'm going to tinker a little bit.
                - Conversely, most use cases are OK for that operation, and the implementation priority is low because it is not the main assumed use case.
        - There are times when you want others to see what you've created but don't want them to edit it.
            - In some cases, the people on the viewing side are also atrophied, thinking that it would be bad if they carelessly manipulate the system and break it.
        - Select Make Read-only URL from the menu to create a new URL
            - The person who opens this URL can edit it, but the edits are not overwritten and saved in the cloud.
            - You can also save the edited data as a separate map by using Save as New Map.
                - I can give feedback like, "You organized it this way, but I think this sticky belongs here."

    - Scrapbox / Gyazo integration
        - ![image](https://gyazo.com/e3782ff51d483d9ad7aa99c80d179393/thumb/1000)
        - If you put the URL of a Scrapbox page in a sticky, it becomes a link to Scrapbox.
        - If it's a Gyazo URL, the image will be expanded.

- About Data
    - Backward compatibility (maps created in older versions should be readable in newer versions)
        - I try to keep it as much as possible because it's inconvenient for me.
        - but it is possible that compatibility will be discarded in the future without notice, or that compatibility will be lost due to bugs
        - For the time being, it is positioned as "something to be used temporarily to clear one's head.
        - Storage Method
            - screenshot
                - The ability to make it in high resolution would be nice.
            - Export in JSON format will be attached
                - Right now, copying a selection puts JSON in the clipboard, but it would be nice to be able to download the entire map as a file.
                - If you record the date and time, you can open it with the old version at the time of creation.
    - Data is stored in the cloud in a form that can be viewed by developers, so do not write passwords, confidential information, or anything else that you do not want to be seen.




Advanced Features
- Support function for dividing into stickies
- Import from Keyphrase Extraction
- Connection with listening chat system

---
This page is auto-translated from [/nishio/頭を整理するツール](https://scrapbox.io/nishio/頭を整理するツール) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.