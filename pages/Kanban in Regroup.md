---
title: "Kanban in Regroup"
---

- [2020-02-04 I actually did the idea in [[2020-02-04 Regroup+Kanban]].

final form
![image](https://gyazo.com/0757d474ff86fc5e3041da9bb56bd4bb/thumb/1000)
- [https://regroup.netlify.com/#/key=mKmQdr3m4oyOQJXH1uYw&cx=839&cy=2570&top=1448&left=-1610](https://regroup.netlify.com/#/key=mKmQdr3m4oyOQJXH1uYw&cx=839&cy=2570&top=1448&left=-1610)
- Regroup→Kanban, final form.
    - I'm not dancing my heart out because it looks like a mere kanban when it comes to this.
    - The process of putting it all together is important.

flow
2020-02-06
- I'm jotting down ideas on my phone about a development I'll do tomorrow.
    - ![image](https://gyazo.com/70ba2d515847e7cf07e6b4374fc4d911/thumb/1000)
- It's hard to use a smartphone when there are more and more of them, but it's not impossible to move some of them around.
    - ![image](https://gyazo.com/f55879eaf1fb6e567e32408da9ff5c7e/thumb/1000)
- When I open it on my iPad, it looks like this
    - ![image](https://gyazo.com/ece19836a927eb6890c5fc0a2c37726b/thumb/1000)
- Here's how it's organized.
    - ![image](https://gyazo.com/8d5b090070ea42e6808e16ffa5f215fd/thumb/1000)
- I want to group
        - [[Demonstration of grouping in Regroup]]
    - Like this
        - ![image](https://gyazo.com/e64a2ba37a56c40d127d6f2c08c9b2d6/thumb/1000)
    - Only a few can be neatly organized.

Consideration of 2020-02-10
- I'm starting to think that the "one pocket principle" is violated because the means to export from Regroup in text format has not yet been implemented, so ideas written directly to Regroup cannot be exported back to Scrapbox.
- Regroup is not yet in a position to meet the one pocket principle on its own, so I want to write it back to Scrapbox.
- → [[Copy selected text]]

It is written out, but not [easy-to-read order and bullet points

DONE
    - Add close balloon to [Groups with no nameplate
- Thumbnail display when the group does not contain any stickies
- If you drag the background of a group, the entire group moves.
- If you drag a sticky in a group, only that sticky should move.
- I want the menu to appear to ungroup when I click on a group.
- When a sticky or group in a group is moused down, it is treated as a click if it is moused up.
- Clicking on a group causes the group to disappear.
- Ghost covered by balloon clicks.
- You get a menu that opens even if it's not a link.
- Bring up grouping in the balloon menu when selecting a lasso.
    - [[Do not force them to wear a nameplate.]]
- When a drag is started, it should be displayed as a drag in progress.
- If dropped to a group you belong to, just an update of the position.
- Bring up grouping in the balloon menu when selecting a lasso.
- When I click in lasso mode, I want it to be like a normal click.
- If I mouse down on a sticky with a lasso, I want it to be a single sticky drag.
    - [[Indication when there is no nameplate in the closed group]]

    - [[Change handling of mouse events]]

TODO
- I'd rather have the letters in chunks than in pieces when I write them on a path.
    - So it is grouped by default and can be ungrouped after the fact if necessary.
    - What's up with this "grouped paths" display?
        - The yellow on the current sticky might be too strong.
        - If you try it and it doesn't feel right, you can fix it.
        - Proposal to lighten the color or increase transparency
        - → [[Remove the border from the group]]

- I want to copy text on a sticky.
    - Lassoed and copied, text and JSON
    - Text: [[Copy selected text]].

- I want to click even with a pen.

- I want Undo on a path I'm about to write, I mistakenly wrote a line with a drag.

- Positioning of newly added stickies
    - I don't see a way to reset the position of the added sticky, or how to reset it.
    - Do I have to?
        - It stretches all the way down, like a notebook.
        - Scaling will change how many sheets you get out before a line break.
        - I feel like that's fine.
    - → Lose track of where stickies are added if they are off-screen.
        - Reset to upper left if the location to be added is off-screen.
    - It's a hassle if they get mixed up when moving later.
        - I want to skip when it interferes with other stickies, etc.
        - Just apply the decision at the intersection.

- If they're differentiated by hash, they'll be identified at the time of the airdrop.

- When displayed with the group open, it is bulky even though it is folded.
    - If you close a group of children without permission, it is a hassle to open it.
    - I'm currently switching between drawings in the group drawing with my open/close state, but I should probably do an "inherit" on the group drawing.
    - Even if the actual group is open, a closed drawing should be made and that should be used as the faceplate.
    - Display when folded for a group with the group in the upper left corner.
        - What happens if the upper left corner is a group
        - Now it's gone.

- Sometimes a dialog box appears before the canvas drawing is completed, and I wonder if I missed adding a sticky. I wondered if I missed adding a sticky.
    - Let's change it so that it is issued in the handler after the canvas is redrawn.

PENDING
    - [[Should we also hit test while dragging and show what happens when we let go now?]]
    - Specifically highlight groups that receive drops, etc.

    - [[Do we need a hit test at drop time as well?]]
    - If you drop outside the group, take them out of the group.
    - If you drop it in another group, move it there.

- Is it strange that closed groups can be opened with one click?

- Moya Moya Map and Kanban
    - Would it be good if the mounted stickies could be colored?
    - Maybe multiple views would be nice.
    - I made a kanban zone and moved on.
    - Move the stickies in the moyamoya map to kanban to break the moyamoya.
    - Keep the link or duplicate it
        - Even if you duplicate it, you have to realize that "the same thing is over there," so eventually you need a link.
    - But is it equivalent to displaying it on one screen and linking it?
    - The transition in the video is cool, but it's just a look.

- The most recent sticky I added is not synced?
    - Does the fact that prompt is blocking make the race condition more likely to happen?

- Not updating to correct position when moved with two finger gesture
    - It breaks when a two-finger gesture is initiated during a one-finger drag.


---
    - [[kanban work methods]] Maybe I should do that.
        - [[Kanban workflow with Regroup+Scrapbox for Regroup development]]
    - I wrote out the idea and summarized it: [[2020-02-04 Regroup+Kanban]].
        - What I actually thought when I did it.
        - There is a painful delay in writing in the current situation.
                - Resolved by [Faster path drawing
        - Movement with the lasso is sluggish because it is not ghosted.
        - There is also a delay after the lasso move.
        - Palm contact may cause violent screen movement
            - If [[Groups with no nameplate]] is not easily available, it is inconvenient to enclose each group in a box.
            - done
        - Single drag movement mode when mouse down on stickies in lasso
            - done:  [[Mouse down on a sticky in lasso mode should not be a move of the sticky]]


---
This page is auto-translated from [/nishio/Regroupでカンバン](https://scrapbox.io/nishio/Regroupでカンバン) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.