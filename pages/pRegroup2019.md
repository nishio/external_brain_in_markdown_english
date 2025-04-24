---
title: "pRegroup2019"
---

from [[pRegroup2020]]
Regroup2019
---

    - [[Operation Test Items]]

---
Preparing for the demonstration
- Smooth flow of editing link with QR code, and then the person who took the picture can try it out on their iPhone and write it down.

    - [[Do we need unframed text?]]
    - [[Maybe the group doesn't need a nameplate.]]

- Ability to move in and out of groups after groups are created.
    - The inability to do this now has made me resistant to forming groups.
        - Would it be better if we could pick a group and "demolish" it?
        - The question is what to do with the nameplate sticky note.
            - Need to enter the nameplate again the next time it is grouped.
            - If you want to do some serious demolition, that's fine.
            - When you want to add to a group, "take it apart, delete the nameplate, select the lasso including the sticky you want to add, and re-enter the nameplate" is not possible as a hassle.
            - No nameplate is better than no nameplate.
- relevance
        - [[Sticky note selection and compression UI design]]
        - Adding and Deleting to and from Groups
            - [[Drag stickies in and out of groups and rearrange them]]
            - If a group does not open when you drag-drop into a closed group, you can create a trash group, for example, and put unwanted items into it as you go.
            - [[When you want to create a group, the nameplate for that group already exists.]]
- relevance
    - No way to open the middle heading.
        - [/rashitamemo/Regroup v2 First Impression#5de6611c9dc7d80000d0b0a7](https://scrapbox.io/rashitamemo/Regroup v2 First Impression#5de6611c9dc7d80000d0b0a7)
        - This is because the function to change the position of stickies by dragging within a group or move them out of the group is not yet implemented.

    - [[Need a way to put line breaks in stickies.]]



- > When I group stickies, I am prompted to enter the nameplate name, but the text of the previously entered sticky is still there.
    - [/rashitamemo/Regroup v2 First Impression#5de660a49dc7d80000d0b0a4](https://scrapbox.io/rashitamemo/Regroup v2 First Impression#5de660a49dc7d80000d0b0a4)
    - TODO: This is another bug
        - I'd prefer a placeholder.
        - I'm beginning to think it's not a good idea to force people to name their nameplates.
            - Better to have a nameplate, especially when grouping paths, but I was thinking a thumbnail would be fine.



- Parallel move with two finger gesture on iPad -> do the same thing on Mac and it zooms.
    - This is because two-finger gestures are not implemented on the PC, and the Mac default function maps two-finger up/down to wheel events.

- The phenomenon of short dots remaining as garbage
    - I'm assuming that Simplify for too short paths is causing some vertices to be NaN or something.
        - Only one stroke of a Chinese character can be trashed.
        - Short paths do not need to be Simplified in the first place.


- UNDOing a delete will UNDO one path at a time.
    - I think I've implemented UNDO unit control.
    - how?

- Images can be put on gyazo now, even if it means OCR.
    - Images have low priority.
    - I hope you can write it down with a scribbler's picture on it.
        - [[canvas pollution]]

- If you specify a personal Scrapbox in your personal settings, it would be nice if the brackets in the stickies are linked to that Scrapbox

    - [[Create shared links with embedded coordinates]]
        - I want something like [hamburger menu

    - [[Publish editorial pages in Github Pages as a Sandbox]]

    - [[Possible loss" alert if there are unsaved changes]]

- Make sure you don't miss any stickies off-screen.
        - [[Zoom with full view when loading editor]]
        - [[Requires ambient display of off-screen stickies]]

    - [[Mouse down on a sticky in lasso mode should not be a move of the sticky]]

    - [[I want to add images easily.]]

    - [[Rendering process blocks path draw]]

    - [[I want to duplicate a sticky note in a snap.]]

    - [[Balloon menu by clicking on a sticky for editing an existing sticky]]

    - [[External link sticky note]]

    - [[Balloon Menu]]

    - [[Permanent link to sticky]]

    - [[Avoid overlapping stickies.]]

    - [[I want to add more and more notes from my phone with voice input.]]
    - I want to keep putting my thoughts on stickies from my phone.
    - [[Ability to chop long sentences]]
        - [[Ability to create moderately divided stickies]]

    - [[Kick out long sentences to Scrapbox.]]

    - [[Digitized and published maps made during the preparation of lecture materials]]

- import
    - Import of PDF lecture materials
    - Import from text with one item per line
    - Import from Scrapbox (with bullets diverted to positional placement)


    - [[Related sticky suggestions instead of automatic sticky placement]]

    - [[sequence-information assignment]]

    - [[I want to reuse it on other maps.]]

    - [[Would it be interesting to see the reuse pathway?]]

    - [[call-writing]]

    - [[Assigning contextual information]]

    - [[Reuse of fragments not used in the final product]]

    - [[Bug that breaks if you zoom out as far as you can.]]

    - [[Unused knowledge is also structured]]

    - [[Delete paths with eraser (necessary?)]]

    - [[Listing of maps created by you]] Think about it when you need it.

    - [[I want to give a link when no hash is specified.]]

    - [[Updating Paper.js gives me a lot of type errors.]]

    - [[Support for multi-line import]]

    - [[Automatic path grouping]]

    - [[Reload when editing offline to avoid losing updates]]

    - [[Event coordinate system issues]]

    - [[PC version should have shortcut keys.]]

    - [[Paste a large image]]
        - Should there be [[Groups with no nameplate]]?

    - [[Sticky should remember the source.]]

    - [[Zoom limit to the full sticky screen?]]

    - [[copy and paste]]


---
This page is auto-translated from [/nishio/pRegroup2019](https://scrapbox.io/nishio/pRegroup2019) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.