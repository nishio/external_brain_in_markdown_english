---
title: "Kozaneba Development Diary 2021-08-19"
---

prev  [[Kozaneba Development Diary 2021-08-18]]
![image](https://gyazo.com/107bd4bafc8adf5e990a2a8d5575a6e8/thumb/1000)
---

Yesterday I implemented the copy function by selecting a range of text and copying it as text.
- There are some things I want to improve, and I can see how to improve, and some input patterns I forgot to assume, and I'm tempted to continue, but the implementation of the user page is a higher priority.
- I'm tempted to do the former, comparing a task of the type "I've got the functionality implemented and want to improve the quality of its output" to "a user page I've long thought should be there but doesn't exist at all yet".
- ![image](https://gyazo.com/ca78606811aa900613d8a7790b1fa90f/thumb/1000)
- I think it has something to do with this.
        - [[Better off investing in a new S-curve.]]

If I don't write down what I'm thinking, I'm anxious to forget it and want to implement it now.
- The search to find clusters and the search to make it one dimensional at the same time was a mistake.
- Because it is not right to connect words in the upper right direction, although the branches should be connected as a cluster even if they extend to the upper right.
    - ![image](https://gyazo.com/b8cdd03f5e47af787c7580e7cb9b22d6/thumb/1000)
- Clusters should be determined first and then made one-dimensional.
- I still don't support when groups are mixed.
    - It's designed to be expressed by indentation.
- I omitted to take into account the large size of the stickies.
    - Distance function should be distance between edges, not distance between centers
    - In that case, the larger the area of the dent, the closer is the dent to the surface?
    - What if it's not stuck?
    - ![image](https://gyazo.com/0d438fd048acec502dffe860d928d8cb/thumb/1000)
        - C is closer according to physical distance as next to A, but it is more natural that B is chosen

Selection doubled by dragging? Moves, scale dependent?

![image](https://gyazo.com/3764a3109dbfc6ce37787e01c0a0f6fe/thumb/1000)

[/shokai/ clean up UserScript after moving to another project (event version)](https://scrapbox.io/shokai/ clean up UserScript after moving to another project (event version)).
- UserScript is determined by a cross between User and Project.
- Is that really necessary?
    - Especially in Kozaneba
    - YAGNI because I don't feel like I need it.

When using JS code read from a service that distributes JS code (e.g. Scrapbox)
- There is a risk of unknowing updates and backdoors being planted.
- Users want to use imports because they are easy, but they don't realize when the fundamentals have been updated.
- Make import "read, cache, and use" instead of "read the latest".

[/shokai/dogfooding](https://scrapbox.io/shokai/dogfooding).
    - I didn't think of [[user extensibility and dogfooding]] as related, but they certainly are.

---
- The list screen is now ready, title has been changed, and loading display has been added.
- I was going to be able to change the title or delete it from this list screen, but on second thought, why delete it without checking the contents? I felt that it would be better to just have the delete option at the end of the list.
- make the ✅summation better
    - ![image](https://gyazo.com/6a642c431c7205936b2999fcee798d59/thumb/1000)

- Fixed ✅selection dragging bug
    - Drag bugs are scale-dependent
- ✅Text copy group support

Making Tutorials Helpful
![image](https://gyazo.com/6756e2e0e9b67b6d268ad5a7abcbfa9b/thumb/1000)
- We have a lot of convergence of things to do, let's improve the tutorial system and change it to a form where a chapter of help is a tutorial.
    - Now the content is an unnamed list, and the headings are simply headline tags.
    - If we can organize this and mechanically handle the headings, we can create a "table of contents.
    - Tutorials are just reading the "tutorial chapters," which would be
    - It's just in the list now, but make it a list of objects with title and body.
    - Keep tutorial listings separate from the overall listing.
    - I used to resume the tutorial with the hatena on the status bar when in tutorial mode, but there's no point in hiding that hatena when not in tutorial mode, it would be nice to get help from there.
    - First of all, we need to change the inside design to a form that can provide help while keeping the current tutorials available.
    - And I can run automated tests to make sure it's not broken.
- Allow you to proceed by keyboard? YAGNI

removed: The following pages will explain the advanced features and the philosophy behind Kozaneba.

![image](https://gyazo.com/92792948d612218ab6d37f679a48d5d6/thumb/1000)
- It has a table of contents and you can jump from the table of contents to individual pages and back to the table of contents.
- But I left the tutorial table of contents out, and it's a pretty long list, so I wanted to fold it up.

![image](https://gyazo.com/107bd4bafc8adf5e990a2a8d5575a6e8/thumb/1000)

Kozaneba Help
- What we already have
    - Table of contents
    - Welcome to Kozaneba!
    - digital stationery to organize your thought
    - You can open the tutorial
    - Let's add some Kozane!
    - Let's move Kozane!
    - Let's scroll and zoom the Ba
    - Let's click to show context menu
    - Automatic font size adjustment
    - You can ungroup a group
    - Let's select objects!
    - It's not saved yet!
    - Let's enable auto-save!
    - Saved?
    - Tutorial Finished🎉
    - We need the practice to use stationery effectively
    - Don't classify, organize!

- Movement with cursor
- Opening and Closing Groups
- Give the group a title
- Division of stickies
    - I can use it to duplicate and update.
    - I'd like to see it after Replace is on.
- Feedback function

- Make important things bigger.
- Spacebar to full screen
- origin of Kozane

Other
- Updating ReactN during range selection is slow and I want to use only DOM.
- No way to make it smaller if you make it bigger by mistake.
- I'm sure English speakers would like to see a space between the two when combining text in copy text.
    - Need to make it configurable.
- User-defined constants
    - I'd like to be able to put it on the net, but waiting to get it from the net before doing any other processing...
    - Constants should be cached locally.
- There's no way for someone without a wheel to zoom in.
    - Enlarge by b

Anne Group Page

After creating a group, I want to close and title it.

On the finish page
- Send feedback anonymously.
- You can also post in the forum
Announcing that

When I organized my TODO, I realized that I could make the things I need to do bigger and then make them smaller when I'm done.
- ![image](https://gyazo.com/8a08585193ba67fa6416105c029b98f3/thumb/1000)


User-defined constants, wheel sensitivity, etc. are easy because they are determined by the time the user operates the system, but it is difficult to make a sticky note square, for example.
StyledComponent is created based on the constant value. Since these are module-level constants, they are calculated at the time the module is read and are not reflected if changed later.
To make this kind of thing changeable, it would require a delay in finalizing the affected items across the board.

There's a difference between individual hand customization and overall customization in the first place.
- For example, if you want to change the color of the border of a group, you don't want it to change only in your hand, but about all the people who see it, so the data for this customization should be owned by Ba
    - And this is after the ability to share without write permissions.

In that sense, the menu expansion is for me.
- Adding more buttons to the AppBar and
- Change key bindings

Changing the sensitivity of the wheel, for example, should be stored per device because it's basically tightly coupled to the device.
If it's too much trouble to edit on Kozaneba, you could press the fetch button to fetch from a specific URL.

The developer menu, the one I use, is hidden for once, but it could display an extended menu for those who want to do customization.

I just converted it on DeepL and it's not bad.
- [/kozaneba-forum/Make wheel sensitivity configurable.](https://scrapbox.io/kozaneba-forum/Make wheel sensitivity configurable.)

How about posting what you have written in the Japanese forum in the English forum by machine translation first, and then correcting it when you feel like it?

[[pScrapboxAutoTrans]]

As for user extensibility, I was going to set it from the user dialog, but maybe I'll set it from a new dialog from DevMenu for a while.
- It's not a good idea to put it in a place where users can see it until it's done right to some extent.

It's tempting to push the edge of what is technically feasible or not, but that would make the room look like a room with prototypes scattered all over the floor, and most users would not be comfortable, so I need to isolate me.

next  [[Kozaneba Development Diary 2021-08-20]]

---
This page is auto-translated from [/nishio/Kozaneba開発日記2021-08-19](https://scrapbox.io/nishio/Kozaneba開発日記2021-08-19) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.