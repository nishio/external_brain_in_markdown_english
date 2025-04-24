---
title: "Talk about putting books in Scrapbox."
---

from [/villagepump/2023/09/13](https://scrapbox.io/villagepump/2023/09/13)
- Shall we do it? Or not?
    - A feeling of (what?)
    - hmm
    - Oh, I happen to see a careless mistake that splits them into 190 and 832 pieces.
    - 190 sides Ready
    - So let's pretend it's a revelation and do this.
    - Uploaded an estimated 40,000 images to Gyazo
- `You have fired too many requests.`

from [/villagepump/2023/09/14](https://scrapbox.io/villagepump/2023/09/14)
<img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>
- Upload to Gyazo, `Too many requests` after about 10,000 requests
    - [https://gyazo.com/api/docs/errors](https://gyazo.com/api/docs/errors)
    - > API has a usage limit of 12,500 times/day.
    - >  If the usage limit is exceeded, a 429 is returned in the Status Code of the Response.
    - also<img src='https://scrapbox.io/api/pages/villagepump/takker/icon' alt='/villagepump/takker.icon' height="19.5"/>
    - I see<img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>
        - Well, you can't have unlimited uploads and have them used as OCR, so there's a limit.
        - With 12500, well, it's not a problem for normal use cases.
- Now that we know we can't "just upload 40,000 images for now," we need to think about Next Action.
- Upload as well as Get were subject to the API limit.
- In other words, the text has been used up in Upload, and Gyazo has OCR'd text, but it cannot be retrieved.
- For a routine process, "25 additional 250-page books per day" is more than enough upper limit, but the question is what to do during the transitional period
- Well, for now, we can't do the latter stage of the experiment until about 24 hours have passed, so we'll wait.

from [/villagepump/2023/09/15](https://scrapbox.io/villagepump/2023/09/15)
- I wonder if there will be an increase in API quota if I pay extra for Gyazo.
- If I signed up for about 10 Gyazo accounts, I could use 10x API.
    - Genius <img src='https://scrapbox.io/api/pages/nishio-en/takker/icon' alt='takker.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/nishio-en/takker/icon' alt='takker.icon' height="19.5"/>.
    - Gyazo Pro, free for 30 days, you can make as many as you want.<img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>
    - You can't merge them into one account later and say, "Huh? No?" because you can't merge them into one account afterwards.
        - It was. regret<img src='https://scrapbox.io/api/pages/nishio-en/takker/icon' alt='takker.icon' height="19.5"/>
        - Personal Gyazo images.[[Gyazo Teams]]に移行することはできるらしい<img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>
            - I'm going to have to migrate these 10, then I'm going to have to cancel nine.
            - Gyazo Team, the minimum monthly fee was 5,000 yen.
- I thought it would be better to finally consolidate to Gyazo Pro so I would have less to think about, but I estimate it will take about 50 days due to the API quota during the transition period...

from [/villagepump/2023/09/17](https://scrapbox.io/villagepump/2023/09/17)
- `page.lines must be less than 10000 lines`
    - (~_~)
    - Either they just can't import it or they can't get beyond it.
    - Or divide it into about 9,000 lines.
- 14274 items, 2.45 GB, 50 volumes
    - It took three days.
- Changed implementation to split and import long pages.
    - It's done.

from [/villagepump/2023/09/17](https://scrapbox.io/villagepump/2023/09/17)
- Talk about pinching books to Gyazo.
    - I finished fixing all the incomplete data due to Gyazo's lack of Quota.
        - It took 2.5 days.
    - Three groups of 20 books each were created for each new book to be processed.
        - If all goes as expected, we should be able to handle one group per day.
        - Well, there are 1,000 books, so even if we stay on schedule, that's a 50-day course...
        - It's a hassle to think "I have to repair the corrupted data..." or "I've already used up all my money today..." and so on.
        - I'm not sure, but there is a possibility that some of the 20 books are very long, and that they may exceed Quota after all...
        - I've implemented a recovery mode, so in that case, I'll recover the next day and then run a new one.

2023-09-19
- I have a few images that I uploaded 9 hours ago that have not been OCR'd.
- It sounds like a phenomenon where the OCR API call fails with a probability of failure and is not retried properly...
- In the end, only four pages in one of the last books were symptomatic of that.
    - Filled with "OCR not available", what should I do?

---
This page is auto-translated from [/nishio/書籍をScrapboxに入れる話](https://scrapbox.io/nishio/書籍をScrapboxに入れる話) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.