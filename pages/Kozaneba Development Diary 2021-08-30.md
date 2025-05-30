---
title: "Kozaneba Development Diary 2021-08-30"
---

prev  [[Kozaneba Development Diary 2021-08-29]]

About Scrapbox Kozane
- Can't load.
- I'm on Kozane's migration algorithm right now, but this is not appropriate.
    - Specifically, the context menu becomes Kozane's

Scrapbox Kozane is mostly done, so we'll do the rest of the work for release.
- First, stop borrowing event handlers from ordinary kozane.
- I thought that, but the click event is picked up by the canvas mouseup in the first place.
- This is where the click process is changed for each type of target.
- The mousedown process itself is pretty much the same for both Kozane and the group.
    - Instead, it's just a difference of forgetting to implement it.
- Maybe we should annex this one?

Refactoring of events has been completed and menus for Scrapbox Kozane and Gyazo Kozane have been added.
- But there are some things that work in common with regular Kozane, so refactoring the menu first.

Well, the edit menu is not appropriate for Scrapbox Kozane.

Scrapbox Kozane could be implemented, but how to get users to add it?
- I'd probably use paste as a starting point, since it's a form of copying a URL and typing that in anyway.
- [https://developer.mozilla.org/en-US/docs/Web/API/Document/paste_event](https://developer.mozilla.org/en-US/docs/Web/API/Document/paste_event)

I deployed it and got an email from Google saying "it's not good to publish unrestricted API".
- When I followed the instructions and put restrictions on it, it stopped working. w
- It's not enough to only allow `kozaneba.netlify.com`, you have to include `regroup-d4932.firebaseapp.com` as well, otherwise OAuth login won't work.

![image](https://gyazo.com/91019f926449a28cc527aea7e52cb939/thumb/1000)
[https://kozaneba.netlify.app/#view=j5N9La0Cc4EhNNpjcACR](https://kozaneba.netlify.app/#view=j5N9La0Cc4EhNNpjcACR)

I don't like the lack of feedback when I paste.
- attached

edited and cloned.
- I know it's suddenly exposed to the user, but I think it's essential to allow the user to customize the menu.

[https://twitter.com/Foam_Crab/status/1431157524804165635?s=20](https://twitter.com/Foam_Crab/status/1431157524804165635?s=20)
> I felt that Kozaneba smoothed out my thinking very much by giving me the sense of manipulating things with my hands, such as expressing the perspective of the nuances of words in terms of physical distance, and being able to name groups and open and close them.
[https://twitter.com/foldrr/status/1432245268510957568?s=20](https://twitter.com/foldrr/status/1432245268510957568?s=20)
> There is a ZUI-like feeling of being able to do operations that are usually done in the file system (current move) or outliner (zoom) steplessly instead of zeroing in.

> On another matter, pasting the Scrapbox project URL (not the page) and then dragging it opens the crash report. I have sent the reproduction procedure from the crash report here.
- I have not yet decided what to do with URLs that are not pages, but I thought that if I set the general URL to "Kozane for external links," I might be able to achieve "I want to link to a place" together.
- > Yes, I agree. I agree, it would be useful if URLs could basically be "kozane to external links" and some URLs such as Gyazo could be previewed as they are now.

I know a lot of people will try, "I wonder what happens if I post the project URL," so I'm just going to issue an ALERT and say, "You can't do that."

What the external link Kozane should be
- Only displaying URL is not good enough.
- If there is an og:image, I want to display it, if there is a title, I want to use it, etc.
- And if there is a favicon, I want to use it?
- In fact, Regroup had a "Wikipedia sticky note"
- If you have a link kozane, you can link to other places.
    - How to display it.
    - The screenshots are a bit cluttered and don't give much information.
    - Title of the place and indication that the link is to a place
        - You have favicon.

favicon
![image](https://gyazo.com/87e9fb245c4d9d883d9ee0612150988e/thumb/1000)
Well, better than using React's default icon anyway.


The fact that Gyazo Kozane has been created means that handwritten additions can also be made.
![image](https://gyazo.com/dd1196b43036307be019617c15c3cef7/thumb/1000)
![image](https://gyazo.com/5fa76e346d4cb8a79aebf77bdf3d978e/thumb/1000)

Grouping...
- ![image](https://gyazo.com/c08a95bd649beec98ea92c1a76c59346/thumb/1000)
- Oh, I'll be.

It's done.
- ![image](https://gyazo.com/5abdd95826e8f17b3a009bbf0f8ad448/thumb/1000)
- `mix-blend-mode: multiply; border: 0;`
- White background color becomes transparent when using multiply composite.

![image](https://gyazo.com/591adec880980a144fad63e1b9724ef4/thumb/1000)
- Hmmm, the one without og:image would be a disappointment...
- ![image](https://gyazo.com/1ab20ff9a47787164e4fecafcae10fd9/thumb/1000)

---
If you paste the Scrapbox URL into Kozaneba, you can create a Scrapbox Kozane, and when you press the expand menu, all pages within 2hops become Kozanes, and you can move them freely.
![image](https://gyazo.com/8a1b146492af61c7f58dca96ebdfd352/thumb/1000)

I'd like to reproduce it and fix it tomorrow. I want to reproduce it somehow and fix it tomorrow.

- [[Kozaneba Development Diary 2021-08-31]]
---
This page is auto-translated from [/nishio/Kozaneba開発日記2021-08-30](https://scrapbox.io/nishio/Kozaneba開発日記2021-08-30) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.