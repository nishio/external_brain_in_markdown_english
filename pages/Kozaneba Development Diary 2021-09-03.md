---
title: "Kozaneba Development Diary 2021-09-03"
---

from  [[Kozaneba Development Diary 2021-09-02]]
2021-09-03Kozaneba Development Diary

> I was happy to see a series of tweets about the Markdownization of administrative texts, which had about 300,000 impressions, and I was happy to see that some people tweeted about it, drawing me into action, which is the civic tech culture. this. you are the "nobody"! [https://twitter.com/hal_sk/status/1433552759593189377?s=21](https://twitter.com/hal_sk/status/1433552759593189377?s=21)
- I'm going to create a function to import Scrapbox content as Kozane because I need it, but maybe it would be nice to be able to import Markdown as well.

Auto Layout, if you think about it, the system doesn't save on position update, but on user operation, so you don't have to turn off auto save to do it.

release notes
- Fix to make only one user have the right to edit when cloud saving is turned on.
    - When user Y opened a Ba created and read-only shared by user X and saved it as another name, the information that X had editing privileges was saved as well.
    - Therefore, the Ba saved by this user Y was displayed in the place list of user X and could be rewritten.
- Automatic backup to browser's IndexedDB
    - Currently default: off, will change to default: on after using it myself for a while
- Added ability to save backup data to a new Ba
- Fixed padding when the group has a low free space ratio.
    - Solved a problem that made it difficult to click on a group instead of its contents when, for example, 9 kozanes were added.
- Automatic deletion of empty groups with no title

Rebuild Kozaneba Development
- Because it also served as a demonstration for users, it was used in a way that was contrary to its original purpose of "getting your head out of the clouds.
    - I put Scrapbox Kozane and draw illustrations even though I don't need it.
- ![image](https://gyazo.com/ed1b782cc5f75ac38432b464fe1c3b70/thumb/1000)
- Required Functions
- I use it and find it.
    - Functions found in Regroup
        - Handwritten additions
            - Fewer people than expected had iPad+Apple Pencil
            - Hand-drawn "enclosures and arrows" prevent "moving items".
                - putting the cart before the horse
            - A figure that is easy to move should have an "image item" since that is the item
    - Fine Features
        - First, try to realize it with user extensions
            - More samples.
            - Designed to be easily expandable.
        - Placement of expansion
            - I'd love to try it without reloading the browser.

- Scrapbox Link Expansion
    - Only add pages that are not already there.
    - Connect the arrows

- Scrapbox Content Import
    - From BaDialog
    - Options for AddKozaneDialog
    - Ignore code regions
    - Treat indented bullets as a group
    - Hopefully Markdown can do the same.

- Selection textualization
    - Scrapbox Kozane cannot determine the appropriate wording until the default project is determined.
        - Texting is by title only.
        - Create a separate Scrapbox format export?

- I want to scroll the screen with a selection.
    - status quo
        - Selection display does not scroll
    - two-finger gesture
    - At least show the whole thing in spaces.
        - If you can do this, you can "place it at a magnification that allows you to see what's inside, use the overall zoom to place it in the proper position within the whole, and then go back to the original viewpoint".
- Manage selections without ReactN

Multilingualization of tutorials
Paste from Regroup
Additional user rendering methods

Arrow function
Tablet Support
Keichobot

Add yesterday's [[Arrows are a way to express clear relationships and make them unbreakable]] to Ba about arrow functions and organize
- [https://youtu.be/5aYxi_l3IJk](https://youtu.be/5aYxi_l3IJk)

![image](https://gyazo.com/9a23774ba94b281eff638253525d8529/thumb/1000)
In other words, "If the dependency is a tree, it's fine" and "If it's circular, it's bad" are resolved as "We just need to make a bipartite graph".
- ![image](https://gyazo.com/fedbceccc7836eb80c868172d7b5fb87/thumb/1000)


I called it an arrow function, but even arrows need to "switch between double and single arrows" to begin with.
- Without a head on both sides, it's just a line.


This week's summary
- Scrapbox Kozane
- picture sumo wrestler
- Reduce unnecessary redraws due to misunderstanding of ReactN hook specifications
- Copy and paste a selection (JSON to clipboard so it can be pasted to another location)
- Create backup locally

I made a backup without thinning it out to try it out, and it came out to about 7 megs.
- About Thinning
    - If there's another backup in, say, a second, you can delete it.
        - In other words, the shorter the "time until next backup," the less you need.
        - Just erase them in order of shortest to longest.
    - If it's over 12 hours, it should be eligible for preservation.
        - Even if you kept updating 24 hours a day for a year, you wouldn't get a thousand.
        - About 11KB with "arrow function Ba"
            - 10 times the size, updated 24 hours a day for a year, 110 MB, no problem.

js

```javascript
kozaneba
  .fetch_api(
    "https://scrapbox.io/api/pages/nishio/2021-09-03Kozaneba%E9%96%8B%E7%99%BA%E6%97%A5%E8%A8%98/text"
  )
  .then((res) => res.text())
  .then((text) => console.log(kozaneba.parse_scrapbox(text)));
```

![image](https://gyazo.com/a92410d360f2d6323ad1d0ff685afc90/thumb/1000)
- ![image](https://gyazo.com/dd9a2099d4991c2f40f764a2f0ca5624/thumb/1000)

> [nishio](https://twitter.com/nishio/status/1433740238799572998): put "hit the Scrapbox API" and "parse the given string with scrapbox-parser" on Kozaneba's API. But I haven't figured out what to do after this yet.

> [nishio](https://twitter.com/nishio/status/1433741644185047043): Is "`a[b]c[d]e`" good because it would be 5 alternating rows of regular kozane and Scrapbox kozane?

> [nishio](https://twitter.com/nishio/status/1433742430591807495): I made the Scrapbox kozane about 3 times bigger than the regular kozane the other day, but if I keep this in mind, should I have kept the default size the same? Should I have kept the default size the same?
>  No, but considering the way it looks on Scrapbox, the card is not inserted in the sentence, so I added it as a regular kozane and the card is at the end?

> [nishio](https://twitter.com/nishio/status/1433764680435048448): first Cloud Function, the design is clunky. It converts the Scrapbox URL to an API URL on the server side, so you can only hit a specific URL. Either rewrite it so it can hit anything...

> [nishio](https://twitter.com/nishio/status/1433772246380605451): If we create a mutual conversion between Scrapbox and Kozaneba, and then create a mutual conversion between Markdown Kozaneba, we could eventually create a mutual conversion between Scrapbox and Markdown interconversion could be made (typical desktop theory).
- [https://github.com/markdown-it/markdown-it](https://github.com/markdown-it/markdown-it)

> [nishio](https://twitter.com/nishio/status/1433779469777453063): of course I'm not aiming to be a converter, so I'm willing to throw away code notation and tables

- [[Kozaneba Development Diary 2021-09-06]]
---
This page is auto-translated from [/nishio/Kozaneba開発日記2021-09-03](https://scrapbox.io/nishio/Kozaneba開発日記2021-09-03) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.