---
title: "I would like to discuss the design of Regroup"
---

- I went from not being clear on what I wanted to discuss to writing it down anyway.
- I thought I just wrote it down and solved it before I consulted with him, but after consulting with him, I realized that the solution I went through was the best one, surprisingly, because I thought it wasn't good enough beforehand.
- Specifically.
    - I had noticed but unintentionally ignored the idea of using the keyboard for parallel movement [[I would like to discuss the design of Regroup #6077ff00aff09e00008ebf98]].
        - In retrospect, I was subconsciously thinking about when I'd use it on my iPad, and I figured there was no way I'd have a keyboard hooked up to it.
    - In "What else can you tell me about paralleling?" The first question was "Inconvenient to operate on a PC" and the second question was "What's the value? and "It would be nice if it could be operated without stress" in "What is the value?
    - I thought about "what needs to happen" to "operate stress-free on a PC" and realized that shift dragging uses both the keyboard and pointing device, so it would rather be less stressful to complete the shift using only the keyboard.

<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>What would you like to see happen in this conversation?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I would like to discuss the design of Regroup
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>What kind of "Regroup" is this "Regroup"?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Listen first.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>Yes, sir.
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Regroup was originally designed for use with the iPad, using two-finger gestures for scaling and translating. The original problem was that the computer screen is too small for electronic KJ, and the hypothesis was that smooth scaling would solve this problem.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>「Regroup」
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Since I use a Macbook for development, it is more convenient to be able to perform all operations on the Macbook. This is converted to a wheel event.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>Scaling."
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Zooming in and out on the iPad works the same way as Google Maps: "Zoom in and out as an image of the currently rendered content, and re-render after the operation is complete. However, this method could not be used because wheel events do not have an explicit end. The only thing I did was to adjust the zoom value for each arrival of the wheel event. In the first place, the operation on the PC was intended for debugging purposes.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>Scaling."
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I was trying to make a tutorial for Keicho-Regroup integration, and since it is difficult to assume that users have iPads to begin with, I thought it was necessary to make it usable on PCs as well. (I just realized that half of the users use their smartphones to open Regroup on a small screen, so I need to advise them to open it on a larger screen.)
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>「Regroup」
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>So, I wanted to consult with you about what I should do because I find it inconvenient to actually use it on my PC. Before I asked for advice, I thought, "Would it be nice if there were hotkeys because it's a pain to press the mode-switching button?" Or, "Would it be nice to have a key that zooms out to where you can see the whole picture?" But as we talked, I thought that the implementation of zooming in and out was not well thought out in the first place.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>Scaling."
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Ideally, it would be the same two-finger gesture as on the iPad, but there's a good chance that browser apps won't be able to capture it; there's still the problem of people not on Macbooks not being able to use it; the problem solved on the iPad and not solved on the PC is actually parallel shift.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>「iPad」
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>On the iPad, both zooming in and out and translating are two-finger gestures, so even lasso selection mode can be used without switching modes. On the other hand, on the Macbook, I had to switch modes to use it. Shift-drag is rather appropriate for "use without switching modes," but I didn't use it.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>Scaling."
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>In the implementation process, "parallel move mode" was created first, and this is still the default mode. In this mode, dragging a sticky moves it, and dragging the screen moves it parallel. Later, when I wanted to move multiple stickies at once, lasso mode was added, and it seemed silly to switch modes when moving only one sticky at a time, so lasso mode was used to move a sticky at a time. It is now a mode that is used only for parallel movement on a PC.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>Parallel shift.
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>There are two ways to move the viewpoint parallel without switching modes: one is to use the keyboard and the other is to create a mini-map. It would be nice to have a mini-map, but it is unknown how much the cost of drawing one would increase.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>Parallel shift.
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>In terms of eliminating the parallel movement mode, some people are afraid of accidentally manipulating and breaking it, so the default should be a non-editing mode.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>Parallel shift.
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I came to a conclusion before I used any in-depth questions, but I felt my next action was to "prohibit mode switching to parallel movement mode, use it, and find out what I'm not satisfied with.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>Parallel shift.
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>the end
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>What would you like to see happen in this conversation?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>It would have been nice if the current vague awareness of the problem was clarified and the next action was set in stone.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>
- >  I came to a conclusion before I used any in-depth questions, but I thought my next action would be to prohibit mode switching in the parallel mode, try using it, and find out what I'm not satisfied with.
- What kind of "parallel shift" is this "parallel shift"?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Moving the viewpoint to look at different parts of the map.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>
- >  I came to a conclusion before I used any in-depth questions, but I thought my next action would be to prohibit mode switching in the parallel mode, try using it, and find out what I'm not satisfied with.
- Is there anything else you can tell us about this "parallel shift"?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I found it inconvenient to do that on a PC.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>What is it that you value?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>It would be nice to be able to operate and organize stickies without stress.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>
- >  I came to a conclusion before I used any in-depth questions, but I thought my next action would be to prohibit mode switching in the parallel mode, try using it, and find out what I'm not satisfied with.
- How do you know this "parallel shift"?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I forgot about the shift drag function myself, users don't understand it of course, so I need a guide.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>
- >  I came to a conclusion before I used any in-depth questions, but I thought my next action would be to prohibit mode switching in the parallel mode, try using it, and find out what I'm not satisfied with.
- What do you hope will happen with respect to this "parallel shift"?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Stress-free and intuitive operation would be nice.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>What would need to happen to the "parallel shift" for that to happen?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>At the very least, it shouldn't require mode switching. Making the user press the shift key is also rather subtle. Many people are used to keyboard operation through games, etc., so it might be possible to dismiss it as such. The mini-map is also explicit in the sense that you can switch viewpoints, but you have to move the cursor to the mini-map, look at it carefully, and click. Given that, perhaps keyboard parallelism is surprisingly the most promising?
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>As for the "parallel shift," can it be done?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I can try that feature on for you.
<img src='https://scrapbox.io/api/pages/nishio-en/nisbot/icon' alt='nisbot.icon' height="19.5"/>
- >  At the very least, it shouldn't require you to switch modes. Making people press the shift key is also rather subtle. Many people are used to keyboard operation through games, etc., so it might be possible to dismiss it as such. The mini-map is also explicit in the sense that you can switch viewpoints, but you have to move the cursor to the mini-map, look at it carefully, and click. Given this, perhaps keyboard parallelism is surprisingly the most promising?
- Where does this "parallel shift" come from?

[https://keicho.netlify.app/#talk=LrTDWXVO1l9BjNPIOfI6](https://keicho.netlify.app/#talk=LrTDWXVO1l9BjNPIOfI6)
---
This page is auto-translated from [/nishio/Regroupの設計について相談したい](https://scrapbox.io/nishio/Regroupの設計について相談したい) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.