---
title: "Kozaneba Development Diary 2021-08-12"
---

prev  [[Kozaneba Development Diary 2021-08-11]]

Today's Covers
[https://youtu.be/dRpZXCzkd9s](https://youtu.be/dRpZXCzkd9s)

-----
- [[I need to organize what to say at the midterm presentation.]]
- Tutorials will be made available in multiple languages after the implementation of the main functions is complete and the UI and explanations are stable, which is not now.

[/blu3mo-public/basi workshop: writing down interests and finding connections](https://scrapbox.io/blu3mo-public/basi workshop: writing down interests and finding connections).
- > Since I'm here, I tried to do it using Kozaneba.
- I'm sure I haven't written the URL anywhere yet, but that's hilarious🤣.

Rectify a metaphor into a direct metaphor and make it a plain word.
> - If you put the kozane into a rigid subjective classification, they will suffocate and die.
> + Kozane is like fish. If you put them into where they can not swim, they will die.
- The original text of [Classification is not the goal.
> When a card is placed in a tightly defined classification system, it often suffocates and dies.
- [I'm too good at Japanese, so I unconsciously use difficult words, but if I can't convey what I want to say by doing so, it's all over if I can't convey what I want to say.

I wonder if Grammary has a "no difficult words mode" or something.

[https://twitter.com/rashita2/status/1425657676940279814?s=21](https://twitter.com/rashita2/status/1425657676940279814?s=21)
- Composition with information cards

![image](https://gyazo.com/b239e1a3c1d010fddf439e48ea8d8dc9/thumb/1000)
![image](https://gyazo.com/7024d958503a7c7e0290b640701dc049/thumb/1000)
Oh, I thought the second one was OK, but it's not.
I added a third and now I can log in.

![image](https://gyazo.com/1bf3472c99867a762db10fb16ee9e8fc/thumb/1000)
Google Analytics is counting Cypress test runs as new users w
fixed

Thinking about taking a video of me actually using it.
- Difficult to use because the long sentence splitting function has not yet been implemented.
- Thinking about doing it in Regroup.
- I lost track of what I used at the Boost meeting (reusability is...
- I still need a "list of what you've made" for each user, and I'd like to have a search for it.

The tutorial doesn't say how to reopen a saved file."
- certainly
- You should be able to see a list of what you have created with that account.
    - And it should be searchable.
    - The place should be named.

If you're thinking about gathering feedback, maybe the Scrapbox forum approach would be better?
- [/forum-jp/about this site](https://scrapbox.io/forum-jp/about this site).
- [/forum/About](https://scrapbox.io/forum/About)

I took a video of the operation.
- YouTube is mysteriously taking a long time to process and I can still only see SD quality.
- [https://youtu.be/L9epZOpYDb4](https://youtu.be/L9epZOpYDb4)
    - [[Dogfooding a Boost Meeting]]
    - [[Regroup, a tool to support thinking by writing and moving the contents of your mind to organize your thoughts Presentation materials]]
    - [[What would you like to see happen by creating Kozaneba?]]
    - [[I need to organize what to say at the midterm presentation.]]


In terms of how to gather feedback, since the tutorial is in English, why not crowdsource an hour of screen recording?

digital tin can
Unlimited size field
small stature
small bill
scene (of a play, movie, etc.)
knee-swing (gymnastics)

- [[Hope you can find a way to cut an interim presentation.]]
- Start with a demo and conclude with a call for additional features.

Why did you do it this time in Regroup instead of Kozaneba?
- Kozaneba implemented "in and out of groups" first with the idea that technically uncertain items should be verified first.
- This is a feature that was put on hold because it could not be implemented in Regroup, and is beneficial but not essential.
- Features that were essential for this purpose
    - Re-dividing stickies
    - Enlargement of Important Sticky Notes
    - (Import from Keicho)

I'd love to do the demo in Kozaneba though!

It's been about 5 hours and I still haven't finished processing the HD.
- YouTube glitch?
- I found a way to play YouTube at 4x speed, but the key video...
    - [https://chrome.google.com/webstore/detail/smasurf-for-web-browser-e/kbilhcaegfmcpmlnpcogdgfchpodhcih?hl=ja](https://chrome.google.com/webstore/detail/smasurf-for-web-browser-e/kbilhcaegfmcpmlnpcogdgfchpodhcih?hl=ja)
- Find a way to play the video at hand at 4x speed.
    - In AppleScript: [QuickTime Player - Holes in AppleScript](http://piyocast.com/as/archives/tag/quicktime-player)
applescript

```
tell application "QuickTime Player"
	set rate of document 1 to 4
end tell
```


[https://youtu.be/dRpZXCzkd9s](https://youtu.be/dRpZXCzkd9s)

Operation Video Continued
- [https://youtu.be/qf67IkMgw7E](https://youtu.be/qf67IkMgw7E)
- [[Kozaneba Development Diary 2021-08-12#6114ebedaff09e0000577e53]]
    - [[Hope you can find a way to cut an interim presentation.]]
- final [https://regroup.netlify.app/#/key=x1x7DeK6jNs6hpDMPBf5&cx=6638&cy=2623&top=-2600&left=-2400](https://regroup.netlify.app/#/key=x1x7DeK6jNs6hpDMPBf5&cx=6638&cy=2623&top=-2600&left=-2400)

If you watch your own operation videos back to yourself, you'll see the frequent operating errors and problems with the specifications.
- After selecting the lasso, drag on the sticky to move only the sticky.
    - The specification is correct that only some of the stickies in the selection do not move.
- You're missing it after adding a single sticky note.
    - Because the position of appearance is determined by world coordinates and not relative to the screen
    - I'm only adding one sticky in the Add Multiple Stickies dialog.
    - This will be in the upper left corner of the screen.
- Cannot be deleted on its own, so it is enclosed and deleted.


---
This page is auto-translated from [/nishio/Kozaneba開発日記2021-08-12](https://scrapbox.io/nishio/Kozaneba開発日記2021-08-12) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.