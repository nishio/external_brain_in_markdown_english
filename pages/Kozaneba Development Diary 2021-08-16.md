---
title: "Kozaneba Development Diary 2021-08-16"
---

prev  [[Kozaneba Development Diary 2021-08-13]]

![image](https://gyazo.com/cf5f4a0ebd27070f46659d3857c64886/thumb/1000)


---
It was an image of extensibility by users, adding menus and processing with JS, but suddenly there was a bad idea of "turning and gaming background".

I tried hard-coding it anyway.
- ![image](https://gyazo.com/501f49913b0c02e482dac0c6276c3c74/thumb/1000)
- I found out that we need a mechanism to allow users to specify @keyframe, it's annoying.
- [reactjs - React how to specify animation @keyframes and classes locally - Stack Overflow](https://stackoverflow.com/questions/51338631/react-how-to-specify-animation-keyframes-and-classes-locally/51340161)
- ![image](https://gyazo.com/cf5f4a0ebd27070f46659d3857c64886/thumb/1000)
    - [Play multiple CSS animations at the same time - Stack Overflow](https://stackoverflow.com/questions/26986129/play-multiple-css-animations-at-the-same-time)


If the user changes the style
- Change the default style
- Change the style of a particular kozane or group
There are two possible ways to
If the object's style attribute is undefined, use the default one, or if it is a string, look for it in the style list by its name?
I want a guard to ensure that the object entered by the user has the proper structure.
- Specifically, React.CSSProperties

It's going to cause users to fail and make errors.
- The current design doesn't give a detailed error message, it just registers on Sentry, but that's not right.
- Error messages should be communicated to the user during trial and error, and that shouldn't go into Sentry.
- On the other hand, you can't distinguish when a user script creates an inconsistent condition that results in an error after the fact.

-----

> Future Flow
>  User testing is at a slow pace as my capacity is overflowing.
>  First, implement the functionality you need for your own use, and then cover it with proper automated tests before including it in the tutorial.
>  After all that is done, we will make the tutorial multilingual and create a user forum.
>  Long-term goal is scalability by users

>  I'm a little slammed with deadlines, so next week I'll sit back, clean up the code, cover it with tests, and add explanations to the tutorials.
>  There is no tutorial on how to view saved pages.
>  Not good because the added stickies are placed at the origin in world coordinates.
>  Important: I still don't think it's a good idea to go the route of using the drag-drop API (the look and feel is very environment-dependent).
>  The test itself has been created by trial and error and patchwork, so it's chaotic.
>  I want to make a user page.
>  Need a list of places used in the past
>  Placement of future expansion, etc.
>  I'd like to make a "of course you can use Scrapbox cards as small bills because they're DOM" video as a catchy teaser at the right time.

The reason there is no tutorial on how to view a saved place is because there is no UI for that in the first place.

Clean up the test
- It's in integrations/movidea now.
- Why not just put the cleaned ones in kozaneba?

The tutorial was not initially intended to have titles on each page
- But as I wrote it, the title converged on a certain form

Tutorial Improvements
Title.
Table of Contents
Number of pages to complete
- Now all the pages are being served in the denominator.
- It would even include additional content.
Table of Contents
- Instead of starting the tutorial from the head.
- help menu
    - I want to jump from the table of contents to the target page.

Test Improvement
Dirty because of trial and error.
- A new way to write beautifully.
- Old and muddled writing style.
I'll speak at a workshop the week after next.
I want to keep it clean.

drag and drop
- Change to a form that does not use the browser's DragDropAPI

user page
- List of places created in the past

Organize with Kozaneba
- [https://youtu.be/n0MLqfjpwlA](https://youtu.be/n0MLqfjpwlA)
- I realized that the definition of "functions I need for my use" was unclear.
- What do I need for my use?
    - Not a tutorial improvement.
    - I would like to have the ability to list the places we have created.
    - The phenomenon of the size increasing when dragging is moderately stressful.
        - Because it doesn't move to the position you want it to move to.
    - I keep the original sticky note at the time of the split, but often want to replace it
        - I think a replace button on the dialog would be nice.

---
It's more modest than the rotating gaming kozane, but it can now drag itself.
![image](https://gyazo.com/8b7465cacb87da9aee6a62481823e90e/thumb/1000)
Only Kozane. No group yet.
I thought it would stop working when I zoomed in and out... but it was working fine.

I thought that I must be confusing the world coordinate system with the screen coordinate system, and that if I separated vectors into "world coordinate system vectors" and "screen coordinate system vectors" and distinguished them by type, I should be able to find the bug of the mistake, so I added a type.
- It was a "bug in which a relative vector is converted to the world coordinate system by taking the difference between two absolute vectors in the screen coordinate system.
- In other words, we need four vector types: "world absolute," "world relative," "screen absolute," and "screen relative" (wait
- And another value "CSS position (`{top, left}`)" (no!)

The group's stand-alone drag moved, well, easily.
- (This is because I wrote it so that it would work easily and not have the Kozane-specific offsets.)

However, the in/out decision for other objects while dragging doesn't work.
- mousemove does not cause mouseenter on div B at the back because div A is following at the very front.
- ![image](https://gyazo.com/a49ee0ca7f64ad8dabab8602e61b3f16/thumb/1000)
- Asking on Twitter: when mousemove comes with div A, I want to detect that the mouse cursor is in div B below it, but I can't figure out how to do it.
    - > [Sheile](https://twitter.com/Sheile/status/1427290332836765699): I haven't tried it, but if I add pointer-events: none; to div A at the timing of mousedown, I think I can get div B's I think I can get the mousemove event to fire.
    - >  However, it also prevents div A's mouseup event from being taken, so it's tricky to handle when you let go of it. ......
    - I see, you can ignore pointer events.
    - The move and drag end of div A is taken by mousemove / mouseup of the innermost parent div, so it's ok.
    - ![image](https://gyazo.com/09249092d908662e561575caa974c7a7/thumb/1000)

Context menu no longer appears.
Selecting a range and moving appears to work okay, so I'll do the test from here.

next  [[Kozaneba Development Diary 2021-08-17]]

---
This page is auto-translated from [/nishio/Kozaneba開発日記2021-08-16](https://scrapbox.io/nishio/Kozaneba開発日記2021-08-16) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.