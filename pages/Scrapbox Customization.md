---
title: "Scrapbox Customization"
---

- I've been using "raw Scrapbox" for a little over a year.
- It's time to start covering feature dissatisfaction with implementation.
    - Mamoru" in "Mamoru-ba-ri" means "it is good to be finished" (from "Mamoru-ba-ri" in Japanese)

- This is the place to write "It might be nice to have such a function" when you have an idea.

- Inconvenience in ai-fun seems to be pretty much solved by [/porterapp](https://scrapbox.io/porterapp).

- List and batch delete pages that meet specific criteria
    - I want to check if the generated pages are the only ones whose title starts with SRS.
    - And I want to delete it.

- API to be appended to the page
    - I would be happy to have it, but it seems unlikely.
    - Is browser automation the only way to go?
        - You could force them to make it with browser operation automation.
        - Providing it to other users is a pain in the ass to deal with authentication information, but you can use it exclusively for yourself.

- Add shortcut key
    - JS commands [[UserScript to insert your own check mark with /nekobatoken/Ctrl-c]].
        - I want to add a shortcut key to [[linking]].
    - [/customize/Scrapbox Dynamic Macro](https://scrapbox.io/customize/Scrapbox Dynamic Macro) Example of doing quite a few things

- Insert from JS to body text
    - JS commands [[UserScript to insert your own check mark with /nekobatoken/Ctrl-c]].
    - It seems that [[document.execCommand]] is not a special feature of Scrapbox, but a method that grows in modern browsers.

- I want to link the title when I post a Wikipedia link.
    - More generally, when we have an external link, we want both the external link in the title of that page and the internal link to be included, since the wording in the title is likely to be a keyword.
    - This is what happens with the bookmarklet I'm using now.
        - `[Spaced repetition - Wikipedia https://en.wikipedia.org/wiki/Spaced_repetition]`
        - Much better than raw URL.
    - ideal
        - `[Spaced repetition]([Wikipedia https://en.wikipedia.org/wiki/Spaced_repetition])`
        - Not only will the link I'm about to put up do that, but I'd be happy if Kobito could go around and change it later if he thinks, "Oh, I should have formatted it this way..."
        - Maybe a page-side command could be used to format the page?
            - But the ability to edit multiple pages at once will be useful for many things in the future.

- I would like to be able to link to Amazon more easily.
    - It would be nice to have a one-click page to Scrapbox on Amazon product pages.

- notification filter
    - When I send notifications to Slack, I don't want my updates and other people's updates to be lumped together.
        - I don't want to be notified of my updates, but I want to be notified of others'.
        - Put a server in front of Slack that receives notifications, filters them, and throws them to Slack.

- Automatic backup of JSON
    - Apparently it came in as a standard feature.

- I want to edit outlines on my iPad.
    - There's a gap on the right, and I want the button to float here.

- I want to have "back and forth" links on multiple pages.

    - [[Proposal to add comment function to Scrapbox]]

- Unified tabs and spaces
    - I'm writing JavaScript code on Scrapbox and it's a mixture of tabs and spaces and I rather dislike it.

- Show the date of entry or update like a Github lawn.

    - [[Extracted UserScript]]
    - Uncut version

- Research: What APIs are available for Scrapbox?
    - [/help-jp/API](https://scrapbox.io/help-jp/API)

---
This page is auto-translated from [/nishio/Scrapboxカスタマイズ](https://scrapbox.io/nishio/Scrapboxカスタマイズ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.