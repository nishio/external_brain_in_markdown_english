---
title: "Kozaneba Development Diary 2021-08-18"
---

forum building
> I was wondering if it would be okay to make this a "Request to Kozaneba".
>  If the projects are "better grouped together without subdivisions" and "differentiated by members", then I feel like there should be one group where you put an invite link and anyone can enter.
>  If it's going to be one, why not include not only Kozaneba but also Keicho and "The Intellectual Production Techniques of Engineers"?
>  But then the title of the project would be something like "Requests to Nishio", which is odd.

I think [[Shuhari]] is the word in these situations.
- First of all, try to trace the pattern without thinking about other ways of doing things.
- It's akin to copying scripture in an unfamiliar programming language.
- I have never created a Scrapbox with [[Unspecified Shared Projects]], so I need to experience that first.

I made it.
- [/kozaneba-forum-jp/about this site](https://scrapbox.io/kozaneba-forum-jp/about this site).

Q: Are you considering team use?
- Kozaneba focuses first on promoting his own understanding [[There are three types of diagrams]].

scroll:body
- [https://material-ui.com/components/dialogs/](https://material-ui.com/components/dialogs/)
- (of) good appearance

I'll do a short cut around today.
- I want to use Cmd+Enter to execute the decision button in the dialog.
    - Naturally, there are multiple dialogs, so the decision button of the one displayed needs to be executed.
- Event handlers for the dialog's buttons are not exposed, so registration is required from the dialog's side
    - But there is no need to change hotkeys for each dialog.
        - = Annoying to see as individual hotkeys.
    - Putting the mediator in place or
    - Wait, doesn't Material-UI provide that functionality in the first place?
        - →I have the ability to close with Escape, but I don't have the ability to have an OK handler.
- like this
    - Check "Is my dialog open?" onClick on the OK button of each dialog, and if not, do nothing.
    - Register onClick as a "dialog close mediator
    - When a hotkey is pressed, the mediator is alerted and the mediator hits all onClicks.

Moving the screen with the cursor
- The previous version worked at a fixed 200 pixels, but I felt it was better because it moved half the width of the screen.

Whole view hotkey
- I put the one on Regroup that you said was useful on this one.
- In the Regroup, the full-size view of the cursor position was displayed when the full view was selected, but now it returns to the previous view.

----
functionality you want to add
- I want to be able to execute the OK-like button in the ✅ dialog basically with Cmd+Enter.
- The "entire display of content at the point of opening" that was in the Regroup.
    - I had a kozane in an off-center place and said, "What? It's gone! and you're like, "Oh!
    - ✅Space key to show the whole view
- REPLACE button in the SPLIT dialog

- Create a user page and list of past saves
    - Warn me if I try to close a page I haven't saved?
- ✅Magnification centered on mouse cursor position

- Key bindings and display design can be changed on user pages
- Import from Keicho
- Import from Scrapbox
- Import indented bulleted text as a group
- Sharing with narrowed write permissions

The one I put on but not yet in the tutorial.
- Movement with cursor
- Opening and Closing Groups
- Give the group a title
- Division of stickies
    - I can use it to duplicate and update.
    - I'd like to see it after Replace is on.
- Feedback function

---
What to do next
scroll:body
Overall view at the time of opening
Put a REPLACE button on the "split" dialog.
Listing of places created by creating user pages
The tutorial is now complete.
Release or user test again

I have a feeling that the user page is going to be more expansive than we currently anticipate it should be if we try to create it.

Based on the principle of doing the uncertain things first, the top two can be done on Friday while I have various meetings, but the user page area is going to require a lot of brainpower, so I should start now to take advantage of Thursday when I have more time.
- Before we start creating screens, we first need to do that because we currently do not store the information of the users who created them in the first place.
- Oh, without the ability to give it a title, it's just a list of unnamed places.
    - Can we do that from the user page?
    - Let's make the content of the first kozane added the initial value of the title.

Whether to retrieve the list by search or store the list itself
- Let's do a search first so as not to complicate the situation since it looks like it could be done with a search.
- I want to `db.collection("ba").where("writers", "array-contains", auth.currentUser.uid)`.
- You can do it by setting the security rule to `allow list: true`, but I want to limit it because it is possible to discover other people's ba if you throw a request directly.
- It's done.
    - `allow list: if request.auth.uid in resource.data.writer;`

I can now get a list of the Ba's I have made.
Next, create a user page and display it

---
Scroll:body
✅Overall display upon opening
Add a replace button to the ✅split dialog.


![image](https://gyazo.com/b803615388616cda1eeee6539e2c2eef/thumb/1000)

[/help-jp/release_note_2021](https://scrapbox.io/help-jp/release_note_2021).
- It's a great mess, isn't it?
- [/kozaneba-forum-jp/release-note](https://scrapbox.io/kozaneba-forum-jp/release-note).
- Written by.

We are looking for people who can help us with [/kozaneba-forum-jp/user-testing](https://scrapbox.io/kozaneba-forum-jp/user-testing).
I used Kozaneba to organize the text of this and realized I forgot about this one.
- [/kozaneba-forum-jp/ want to copy the text of a selection of kozane](https://scrapbox.io/kozaneba-forum-jp/ want to copy the text of a selection of kozane).
![image](https://gyazo.com/24578bc9fc4201a30aee625987b3649e/thumb/1000)
- Hmmm....feeling to improve a little more


Bug: Selection move mode after clicking on a selection to bring up the menu and then closing the menu.
- fixed
Selection doubled by dragging? Moves, scale dependent?

---
This page is auto-translated from [/nishio/Kozaneba開発日記2021-08-18](https://scrapbox.io/nishio/Kozaneba開発日記2021-08-18) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.