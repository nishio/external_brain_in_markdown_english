---
title: "Summary for 2021-08-08 Kozaneba interim presentation"
---

[[mitoujr2021]]

status quo
- We have a minimal prototype implementation and one user test appointment next Wednesday.
    - Maybe we could add a few more.
- The name changed again.
    - Kozaneba digital stationery to organize your thoughts
    - There are many reasons, but it's not the main topic, so skip it.

Continuing the policy of "dogfooding the mentoring method itself," we will prepare a video similar to the creators' for the interim presentation.
- But I'm having a hard time deciding what to tell you in the interim.
- We're rebuilding from scratch after the Boost conference.
- The difference this time, the stories about how it was so great to test with Cypress, or how we fell into a few traps, or how thanks to immer we were able to easily implement a specification that was difficult and neglected in the previous version, will be popular with some (who use similar technology) audiences, but won't stick with the rest of us.
- Why was it necessary to rebuild it, what are the issues that need to be examined, and what would be the benefits of building this?
- The reason we had to rebuild it was because the previous version was a trial-and-error process, and there were two problems.
    - Complicated flow for users to start using the system
    - Code complexity
- The steps for users to start using the system are particularly complicated, so writing explanatory text is lengthy and difficult to use by any means.
- This version has been reorganized and now includes a tutorial. This is not a tutorial of the type that constrains operation, but rather serves as help that can be viewed on the same screen at any time.
    - It's especially nice that GyazoGIFs can now be used to put up videos.

- What are the issues to be verified?
    - In short, can you start using it without me verbally explaining it to you?
    - Especially non-Japanese speakers
    - If you can't begin to use it, you can't begin to value it.

- What it would be like to be
    - This one could be torn apart.
    - For me personally, if I can create a tool that is easy for me to use, that's all that matters.
        - If you're going to pivot on that, then it doesn't matter if other people can use it without explanation.
    - If you twist the content consistent with what we're doing now.
        - We want to raise the intellectual capacity of people around the world.
        - That's a big deal.
    - Dazed and Floating Related
        - The "Intellectual Production of Engineers" in the process of being translated.
        - Machine translation of my Scrapbox with over 10,000 pages
        - Why do you feel that there is a connection between these?

8/8
- [[What would you like to see happen by creating Kozaneba?]]
- When you have a tool that is easy for you to use, that's all that matters.
    - Sometimes you can learn by watching other people use it and thinking, "I see, that's a good way to do it.
    - To get that kind of learning, it needs to be used by a diverse group of people with different background knowledge.
        - This is the need for this to be used by people overseas who may never have heard of the KJ method or the Kozane method.
        - I noticed something incongruous when I wrote "English-speaking" for "overseas."
            - I'm making it in English because I'm better at English as a first step, but it could be inherently important to have a high-density notation method of information in Chinese characters, which is why the Chinese-speaking world is looking more attractive.
- > "The Intellectual Productivity of Engineers" in the process of being translated.
    - [/nishio/multilingual development based on machine-friendly English](https://scrapbox.io/nishio/multilingual development based on machine-friendly English).
- > Machine translation of my own Scrapbox with over 10,000 pages
    - My output speed is Japanese>English>>Chinese, but I would like to increase the output accessible in Chinese (I have some books, but they are too slow on their feet and have strong advantages in being searchable).

We're getting connected!
- I would like to add to the intellectual production techniques of engineers.
        - [[(5.2.4.6) Family resemblance]]

Summary of progress since 6/25
- 2021-07-02
    - done
        - Cypress and ReactN can be combined for testing.
        - Parallel translation scaling with touchpad
        - Drawing groups (basic)
        - Import from JSON in Regroup
    - doing
        - When importing from JSON in Regroup, the position of stickies in a group is not correct.
        - The ability to display enlarged stickies was not yet available.
- 2021-07-09
    - No progress
- 2021-07-16
    - Test by updating status with immer.
    - TypeScripting of test code
    - Drawing group title function and opening/closing
    - Display of nested groups Imported from Regroup now displays correctly.
    - I added a menu bar, menus and dialogs.
    - I can now bring up a menu when I click on a sticky.
    - Group drag implementation
- 2021-07-30
    - URL routing change
        - Assign a new URL to the page for testing
        - After accessing the route, I can now start the tutorial (the tutorial itself is not yet available).

    - Drag in and out of groups.
    - nested group

    - Adding Sticky Notes
    - Group/Ungroup a selection
    - Delete: delete group, delete stickies, delete selected items at once

    - Cloud storage function (on the way)
- 2021-08-06
    - Rename: Movidea→Kozaneba
    - Test Release
    - Cloud Storage
    - Testing Firebase Auth with Cypress
    - Testing Firestore with Cypress
    - Tutorial in progress


---
This page is auto-translated from [/nishio/2021-08-08Kozaneba中間発表に向けたまとめ](https://scrapbox.io/nishio/2021-08-08Kozaneba中間発表に向けたまとめ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.