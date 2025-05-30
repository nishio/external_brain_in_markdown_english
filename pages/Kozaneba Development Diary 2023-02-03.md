---
title: "Kozaneba Development Diary 2023-02-03"
---

prev  [[Kozaneba Development Diary 2023-01-25]]

2023-02-02
It's a pretty destructive rewrite, but at least I can now observe what happens when I turn off automatic font size adjustment.
- ![image](https://gyazo.com/98982a33a6751566c08afe60884e34a1/thumb/1000)

The "bounding box" when a range is selected or a line is drawn does not match the actual appearance of the box.
- ![image](https://gyazo.com/61564c7a5390c089bc7a3d5203e3294d/thumb/1000)
- If we want to solve this, we need to get the actual size by accessing the DOM by those codes, or we need to get it at the time of rendering.


2023-02-03
I tentatively named it "[[Fixed font size function]]" because it is difficult to refer to a concept without giving it a name.
- This is hard to see the value to the user, so we will eventually rename it.

Future Work
- Fixed font size is currently being experimented with in a pretty destructive rewrite.
    - They're achieving this by breaking the original font size adjustment feature.
- I challenge you to make this a feature toggle.
- Once it's done, make it "a feature that is turned off for the general public but can be turned on for advanced users because it causes problems with range selection and line merging".

It could coexist with automatic font size adjustment!
- ![image](https://gyazo.com/ce81250e9ac8d91c6ce5941a251ae181/thumb/1000)
feature toggle
`kozaneba.constants.exp_no_adjust = true`
Kozanego's flag for whether to turn off auto-adjustment is "whether the first character is # or not."

Let's use it in this state for now.

![image](https://gyazo.com/653117636492ca9aa77c28242bd147d6/thumb/1000)
- Bug.
- Fixed.
    - ![image](https://gyazo.com/64f73e37e119678b0d4ca3f31a62e520/thumb/1000)
    - No release yet.


Notes on thoughts
- User scripts, saved to browser local storage, disappeared.
    - Well, I'm saving it separately as a sample, so there's no damage, but it's hard to tell with that kind of behavior.
    - It is technically possible to store the settings tied to the user, the reason why we haven't done it is because there was a need for "different settings for different devices" like a Macbook with a touchpad and a Windows with a wheel mouse.
    - However, there is a sense that only flags are needed to separate settings for each machine.
    - I haven't tried it myself because it doesn't work properly on my iPad after all, but I've also accessed it from my iPad and iPhone.
        - For example, you could just add what comes to mind on your iPhone while walking around, and then organize it on your PC when you get home, like you can see it but not edit the map.
- It would be a good idea to check for duplicates when they are automatically added, such as in the Scrapbox Kozane expansion.
    - In other words, if you put one up and expand it, it's great for organizing your Scrapbox! Like this...
- I have a presentation next week and will use this to organize the information.



---
This page is auto-translated from [/nishio/Kozaneba開発日記2023-02-03](https://scrapbox.io/nishio/Kozaneba開発日記2023-02-03) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.