---
title: "Sticky note selection and compression UI design"
---

    - [[Lasso selection of stickies and paths]]  done
    - [[Grouping of selections]]  done
    - [[Display of nameplate]]  done
- Group open/close done
    - Open a closed group with one click.
        - I've looked at the Move tool that is chosen by default to achieve this.
            - I'm branching out like what is clicked is Group or Path,
            - We need to clean it up with the type information we defined earlier and then add the functionality.
        - Enum.
- Group move done
    - When a group is grabbed and dragged, it moves while being dragged, but returns to its original position when spoken.
        - This is because updating the coordinates of the group is not implemented.
        - Instead of changing the position of the group, we decided to change the position of the child elements
                - [[Recursively update the position of child elements of a group]]
        - Because it would be better to know the location of an object by looking at the object itself, without having to go back to the parent, so that [[connector]], etc., can be used later.

    - [[Drag stickies in and out of groups and rearrange them]] This is still
    - [[Editing a nameplate]]  done


-----
I wondered if I could enclose each element sticky with a lasso around an open group, but that was no problem.
This is because the target of the lasso hit judgment is limited to objects at the top level of the layer.
I think this is a good idea to keep this specification.
- Group not selected, at least should be selected when closed


    - [[Balloon Menu]] is on hold.

- Is it subtle with the current "what is drawn is put in Array in the order in which it is drawn"?
    - When saving in Firestore...
    - I'll think about that later, it should be ok to convert on save/load

I wish I could enter pen input directly into stickies when I group them and enter the front cover edit mode.
- It should be completed to the end with text input first.
- I was thinking, "I don't like the idea of using a keyboard on the iPad," but now I have the option of voice input.


----- discussion
- Groups must be easy to open and close
    - [[grouping#5bd6d729aff09e000076a600]]
    - Don't take the trouble to check what's inside.
        - A: Open and close with one tap on the nameplate sticky
        - B: Ring menu around the nameplate sticky

- Groups don't have to be explicitly created.
    - Explicit group affiliation relationships require in, out
    - When moving in batches, you can specify which one is to be folded for the first time when folding.
    - The target to be moved collectively is not necessarily a group.
- ⇔ Groups should be explicitly created
    - The process of putting up a nameplate is important +1

- [[ReGroup2018#5b72e0e2aff09e000000883c]]
    - grouping
        - You can use "Bundle mode start button→tap (toggle) the target sticky→done button/cancel button".
        - I just created a lasso tool and it has the same number of moves as "lasso mode", "selection", and "grouping".
        - procedure
            - Bundling mode starts
            - Tap the target sticky
            - Finish button
            - Select a nameplate or create a new one
- ⇔ A lasso tool would be needed.
    - Needed even for simple transfers, unrelated to grouping
    - Select then Compress button
        - So the nameplate sticky is created and go to edit mode.
        - [[Compression and decompression of stickies]]
        - Select
            - I'm thinking of a choice +/-, but I wonder if it's necessary, or if you don't need it if you have a lasso.
        - Drag on the nameplate to move the entire nameplate
            - Do you need it?
        - Open.

- [[What should happen when a compressed sticky is decompressed?]]
- Proposal 1: Repulsion by physics
- Proposal 2: It doesn't have to be a Euclidean space.
- Idea 3: Zoom out what doesn't fit
- ⇔ No
    - When you tap on a crowded nameplate sticky, it takes a second to zoom in to see a small, unreadable sticky.
    - Since it is obvious that the intention of tapping a nameplate sticky is to "check its contents," it should be displayed in a way that allows the user to check its contents most easily without additional operations.
    - It's probably an overlay.
        - ![image](https://gyazo.com/bb85089b7974fce7436609ca922f976f/thumb/1000)
            - [[Compression and decompression of stickies]]
            - Drag and drop to open groups to add and delete to groups
                    - [[UI for adding and deleting stickies in existing groups]]

[[pRegroup-done-2019]]

---
This page is auto-translated from [/nishio/付箋の選択・圧縮 UI設計](https://scrapbox.io/nishio/付箋の選択・圧縮 UI設計) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.