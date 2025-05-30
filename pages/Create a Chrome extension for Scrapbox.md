---
title: "Create a Chrome extension for Scrapbox"
---

- [[Scrapbox Customization]]

- Create a Chrome Extension
- Create something that maximizes the needs of one person, not something for many people to use.
- Allocated [/nishio-custom](https://scrapbox.io/nishio-custom) instead of namespace
    - Use like /nishio-custom/sort

- Research: How Chrome Extensions are Made
    - [Getting Started Tutorial - Google Chrome](https://developer.chrome.com/extensions/getstarted)
    - I guess I should just read this for now.

- Feature

    - [/sushitecture/Scrapbox API story to play with](https://scrapbox.io/sushitecture/Scrapbox API story to play with).
        - API return values, etc.
        - Arbitrary positioning of pages
            - As a [[KJ method]] user, I'd be stumped if it worked well enough.
        - Low priority
            - The KJ method can be used universally, not just for Scrapbox, but if you realize it with the Scrapbox extension, it can only be used for Scrapbox.
            - It's useful to be able to do KJ method on iPad~.
                - Independently with Scrapbox
                - Separate page for later.
        - It would be nice if a Chrome extension could extract the DOM from Scrapbox and import it into the KJ Method app.
        - If you have a group of people in a bundle and you put a nameplate on it, it would be nice if you could add a link at the end of each hige if it is Scrapbox.

    - Slider to hide deep in the tree
        - [/customize/Hierarchy Extension](https://scrapbox.io/customize/Hierarchy Extension)
        - This is especially useful when planning the structure of a book, because you can hide the details and view the entire book.
        - (I would like to see it included as a feature of the main unit.)

    - include
        - Replace include links in a page with the linked content individually or in batches.
        - When creating a book manuscript, you can create pages in sections and review them together in chapters.
        - I haven't been able to use Scrapbox stiffly enough to write books because of this lack.
            - Lack of power when trying to structure information on a book scale
        - It's unknown if this feature would solve the problem, but I'd like to experiment.
            - [[I want to write a book in Scrapbox]]

- Options other than Chrome Extensions
    - Native application with Electron?
        - Mainly a desire to do something interesting by touching the local file system.
        - [Let's build an application with Electron - Qiita](https://qiita.com/Quramy/items/a4be32769366cfe55778)
            - Some people don't like to put in local app passwords.
    - What about PWA?
        - [PWA and AMP - Qiita](https://qiita.com/edwardkenfox/items/4c0b9550ffa48c1f0445)
        - It doesn't seem to be suitable for "extending the functionality of Scrapbox", which is what we are trying to do this time.

---
This page is auto-translated from [/nishio/Scrapbox用Chrome拡張を作る](https://scrapbox.io/nishio/Scrapbox用Chrome拡張を作る) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.