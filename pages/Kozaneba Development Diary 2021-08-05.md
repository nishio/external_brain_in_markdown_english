---
title: "Kozaneba Development Diary 2021-08-05"
---

prev  [[Kozaneba Development Diary 2021-08-03]]
Today's Picture of the Day
- The tutorial is starting to work.
- ![image](https://gyazo.com/a4694adb57cf2039b01f4f11ffee0ae7/thumb/1000)
---
Yesterday's Summary
- Let's be honest and configure the Local Emulator Suite, because it's not easy with weird third-party tools and you'll get into mysterious errors.
- Auth can now be tested.
- Firestore Testing
    - Write Firestore rules file
    - Install Java separately and manually
    - Unable to save objects created on the Cypress side
        - Due to being separated by an iframe.
    - ExperimentalForceLongPolling must be set to true
        - You need to do this before you useEmulator.

---
How should I test the status of logging in or saving the network in progress, because it doesn't appear on the screen?
- Create a debug display DOM to test?
- You can test by putting an icon on the status bar, adding tooltip text to the icon, and then adding testid to the tooltip text!
- Killing two birds with one stone by helping humans?
    - ![image](https://gyazo.com/ee03a126afe38b1cc65ffa9b38c57660/thumb/1000)

Update to Cypress 8.2
- ![image](https://gyazo.com/ca0f97d83abcb69faf3c294b23e55abe/thumb/1000)
- I've been getting these warnings for a while now, but I don't know what to do.
- I've updated VSCode to show the list of devices on the right, so it's easier to see when starting up a full process, and I'm naming them manually.

Cloud storage is now available.
- I was able to get him to log in and then save.
    - I'd have to create a tutorial before implementing a complex scenario with multiple devices and multiple users to test users.
- If you trigger the save manually, you can see what has been saved.
    - If you keep it open in another tab, it will auto-update as well.
    - I'm testing manually because it's hard to test something with multiple tabs, a little scary.
- If I make it so that it automatically saves when it is updated, I need to make sure that when the data comes from the server and is updated, it does not trigger the save.
- For some reason, I had a phenomenon where I couldn't put small bills in a group only when I read the cloud-saved ones, and it took me a lot of time to solve it.
    - I'm mistakenly destructively updating objects passed via React props, and the ones via props are `isExtensible: false`.
        - [Object.isExtensible() - JavaScript | MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/isExtensible)
        - [TypeError: can't define property "x": "obj" is not extensible - JavaScript | MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Cant_define_property_object_not_extensible)
    - It's puzzling why it was fine until I saved it to the cloud and then it became `isExtensible: false`, but I fixed it because it was a mistake to destructively update something that was not a snapshot of the immer in the first place.

![image](https://gyazo.com/afe024068b9f42f1aa04b1fe404daa5d/thumb/1000)

![image](https://gyazo.com/a4694adb57cf2039b01f4f11ffee0ae7/thumb/1000)
Tutorial is now working.

The way it works now, I can't open the tutorial dialog while other dialogs are open, is that inconvenient?

When I finish Kozaneba, I would like to find a design that can synergize Kozaneba with the English translation of the book "Intellectual Production Techniques for Engineers" that is in progress, and with the machine translation of my Scrapbox project.
- Since the UI is in English, the explanation is also written in English, and come to think of it, I was in the middle of translating it.

Tutorial Continued Content
- Let's add a small bill.
    - I want to open the tutorial dialog with the add dialog open here
    - I'd also like to improve the add small bill dialog a bit more.
Added.
- Drag and move groups
- Drag them out of the group.
- group (e.g. members of a group)
Add again
- Words, short phrases, slightly longer phrases, longer sentences
- Talk about automatic font size adjustment.
- Talk about making it not too long.
    - (When we have the ability to disassemble after the fact if we make something too long, which we don't have yet, we will explain it here.)

Fill in about 50 lines of text.
- You can pour in whatever you like, but for those who are not prepared to do so, we provide the explanation so far for pouring in.

Preservation.
- At the moment, sharing a URL gives you editing privileges, ReadOnly sharing will be added soon.
Other
- I'd recommend anyone who opens it on a phone to do it on a larger screen, maybe page 2.

next  [[Kozaneba Development Diary 2021-08-06]]

---
This page is auto-translated from [/nishio/Kozaneba開発日記2021-08-05](https://scrapbox.io/nishio/Kozaneba開発日記2021-08-05) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.