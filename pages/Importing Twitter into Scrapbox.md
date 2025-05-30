---
title: "Importing Twitter into Scrapbox"
---

Go to Twitter Settings, "Request All Tweet History" and wait for a while, then the download link will be emailed to you.

Be careful when you unzip, it will be extracted to the same location as the zip without digging the directory.

I had made a conversion script before, but after about a year, I changed my mind about the preferred conversion method, so I'm reworking it.

A year ago I tried to add the ability to automatically turn keywords into links.
- Now I'm not a fan of automatically turning keywords into links.
- If all the keywords were to be links, that would be the same result as if you had searched for them on the search page.
- There is an optimal state between the extremes of "no keywords are linked at all" and "all occurrences of that keyword are linked."
- Automatic linking does not yield optimal results.

Last time I made a page for each tweet, but not preferable.
- Difficult to see tweets before and after, so context is disjointed.
- Grain size is too fine.
- I think it's better to put it together on a day-by-day basis.
- Sort in order from oldest to newest
- I was going to put the time on each Tweet, but the Tweet older than a certain date doesn't contain the data of the posting time.

So source [https://github.com/nishio/twitter_to_scrapbox/blob/master/t.py](https://github.com/nishio/twitter_to_scrapbox/blob/master/t.py)
Import Result [/nishio-twitter](https://scrapbox.io/nishio-twitter).

I checked this time and it was possible to delete the project and then create a new project with the same name.

---
This page is auto-translated from [/nishio/TwitterをScrapboxにインポートする](https://scrapbox.io/nishio/TwitterをScrapboxにインポートする) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.