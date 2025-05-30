---
title: "Export Method API"
---

    - It would be good to have [[API]] in [[Writing Method]].
- I was thinking of [[dumpfb]], which writes Facebook activity to a file.
    - [[node-webkit]].
    - Consider using [[Puppeteer]] in new version
    - I don't want to hardcode my Facebook password.
    - In the previous version, a window would appear, so I had to manually log in to Facebook and then launch the export.
    - Can you put up a window? →Yes, I can.
    - Or rather, it should be a Chrome extension.
    - I wonder if a Chrome extension can export files (see [chrome.fileSystem](https://developers.chrome.com/apps/fileSystem)).
    - No, wait, since we're going to create a service called "write out method -> make it into a KJ method sticky" soon anyway, why not just provide an API for the write out method?

- With this API, it's not just about Facebook activity.
    - Twitter (my own and others')
    - When you see someone else's Scrapbox or Wikipedia, automatically clip it
    - Clip from Amazon
    - Of course, it can be used for the write out method (= manually get it out of your brain)
- The amount of work is overwhelmingly larger than the manual export method (= not assuming that a human being will see all of it).
    - I don't even look at the entire current Twitter timeline.
    - Chronological order (most recently added first)
    - Display for Review
        - Incremental Reading-like display
        - Do not display items with a date close to the last display date
        - A gumbo that might yield something new."
    - search (e.g. for someone using a search engine)
        - Shouldn't the search also be recorded as an activity?
        - You should be able to create tags and groups after the fact.
    - You can "Like."
        - Keep the "like" and "view" values and use the "like/display" count as a measure of goodness
    - A reply button allows you to comment while keeping the link.
        - One click to quote the original text, so when you want to edit it, reply with a new text instead of editing the original.

[[Cloud Firestore]]

---
This page is auto-translated from [/nishio/書き出し法API](https://scrapbox.io/nishio/書き出し法API) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.