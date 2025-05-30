---
title: "Chrome extension to auto-scroll Scrapbox"
---

- Scrapbox automatically scrolls and jumps when it reaches the end of the page, following a random link.

- When a page is opened, it stops for a while and then scrolls automatically.
- When you get to the bottom, follow the link to jump.
    - Jump destination is randomly selected from hover and top page
    - The top page is included in the random jump destination, so even if you get stuck in a place where only a few pages link to each other, you have a reasonable chance of escaping.
- Stop operation for 1 minute when mousemove or keydown is detected (screen saver-like operation)
    - Now it's working even if the focus is off the window. Should I use `$(window).blur` to determine if it has focus and stop it?
- Scrapbox's autoscroll auto-jump extension, I thought it was jumping to unconnected places, but there are 207 .hover and .page-list-item on a page that looks like it has only 7 links, so how do I get the ones that are actually linked to the page? I wonder how to get the ones that are actually linked. In the meantime, it seems possible to lick them all and use .is(':visible') to determine which ones are actually linked.

- [Github](https://github.com/nishio/scrapbox-autoscroll)

-----
2018-08-11 Comments
- Screensaver-like functionality is not very good.
    - Animation does not stop immediately due to the fact that it is timed and continues for a specified period of time.
        - There may be a way to stop it, if you look for it.
    - Scroll bar operation is not considered to be in focus, causing the bar to pull together.
    - Starts moving in 1 minute, too fast for everyday use.
        - Obviously, there should be a clear separation between display and everyday use.
        - For display = image not edited
- There is a list of pages under window.scrapbox


ver0.5
- Stops when out of focus
- In addition, when the focus is lost and returned, the same countdown occurs as after a page transition.

ver0.4
- Fixed scrolling bug
    - > I think there is a phenomenon that after the "page that shows everything without scrolling" is displayed, all subsequent pages will transition to the page without scrolling.
    - When the scroll position was the same as the previous frame, it was judged as "no longer scrollable = end of page", but now it tries to scroll for 3 seconds.
    - Released.

ver0.3
- If mousemove or keydown is detected, stop operation for 1 minute
- The current position used to scroll to "memorized current position + 200", but now it scrolls to "actual current position + 200".
    - Because fast scrolling or reverse scrolling was occurring after the user performed an operation such as scrolling
- I continue to have problems registering with the Chrome Web Store. What is wrong?
    - > (tokoroten) chrome store can log in with any google account, but the primary google account is used to upload files, so the account is different there and the upload fails.
    - That's it!
    - [Available to the public at](https://chrome.google.com/webstore/detail/scrapbox-auto-scroll/oopejekobiompfoiomenkcdhbeiecngn)
    - But by mistake, it's ver 0.2.

-----
ver0.2
- [Github](https://github.com/nishio/scrapbox-autoscroll)
    - About 40 actual lines [https://github.com/nishio/scrapbox-autoscroll/blob/master/src/content_script.js](https://github.com/nishio/scrapbox-autoscroll/blob/master/src/content_script.js)

- I tried to register with the Chrome Web Store.
- > An error has occurred: The item could not be processed.
- >  A system error has occurred in the Chrome Web Store. Please try again in a few minutes.
- so I'll wait for now.

- In the future, it would be nice to have something like a screen saver that stops when you move the mouse or keys, and starts moving again when you leave it inactive.
- Also, I made it with the Chrome extension for now, but it would be interesting to do something like leave it displayed on an iPad, so I'll figure out how to do it on iOS.

---
This page is auto-translated from [/nishio/Scrapboxを自動スクロールするChrome拡張](https://scrapbox.io/nishio/Scrapboxを自動スクロールするChrome拡張) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.