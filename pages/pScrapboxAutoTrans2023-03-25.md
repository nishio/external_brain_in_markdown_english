---
title: "pScrapboxAutoTrans2023-03-25"
---

2023-03-25 [[pScrapboxAutoTrans]]

Whether to put the translations in this Scrapbox or not.
- I have a whole book's worth of content in English at [[Engineer's way of creating knowledge]], but almost a year later, I haven't experienced any "connection! I have not experienced any "connection" at all!
    - Sometimes the connection is unexpected, but it's not a happy connection.
- If the translation is immediately added to this Scrapbox as a separate page, there will be two similar pages in a row
    - the other
- Provide both Japanese and English on the page.
    - I think this is better, but not better.
- Fundamentally, the problem is that the page list is not customizable.

- [[English Transmission Support]]
- > How about writing something casually in Scrapbox, automatically machine translating it, posting it to the English version of the Scrapbox project, and then tweeting it out on an English account so that I get notified when there is a reaction and [[Social Triggers]] are triggered?
    - [" Tweeting with an English account
    - No reaction on Twitter.

- [[Scrapbox Englishization Plan]]
- > Scrapbox's API seems cumbersome to achieve sequential updates.
    - Yes
- > As a small start, you could first export it in JSON, translate it, and import it.
- > Insert `(auto-translated from [Japanese http://....])' in the first line? and insert `(auto-translated from [[Japanese ]])' at the beginning of the line?
    - Mechanical text on the first line makes the card display [[trash house]].
    - Iconic notation if you want to put it at the beginning

- [[ScrapboxAutoTrans Development Diary 2021-12-28]]
- > In the future, it would be good to use Github Action to spit it out as a static file and host it on Github Pages or something.
    - Well, at least I'd better diversify my domains because they might not pay for the maintenance of the nhiro domain after I'm dead and they might notice that I'm dead after I'm gone.

2023-03-26
stay awake during sleep

The problem is complex.
- How to translate documents that are updated daily
- How to show what has been translated
- Where to place the translated
- [[Divide into simple problems]].

I'm getting to the point where I can use Github Action to get it.
- Can I keep the translated data too?
- Is there something already in English that doesn't need to be translated?
    - You have manually translated content.

- estimate
    - 13,115,848 characters
- from  [[Engineers' Intellectual Production Methods English Project]]
    - > I exported everything and estimated that it would cost [60,000 yen to translate everything.
- from  [[Cost of machine translation]]
    - > ¥2,500 per 1 million characters
- Whether character is a Unicode character or bytes
- 27,493,421 for bytes.
    - This one is closer to the last estimate.
- Estimated at less than 70,000 yen
    - Feeling that it is less than 1% of annual income and will pay for itself in one year if productivity improves by 1% in the coming year.
- execution (e.g. program)
    - I ran 300 pages and it was $400.
- Whole execution in progress
- memo
    - I had left it for almost a year thinking about the details, but then I realized that [[procrastination]] was no longer an option, so I decided to do it today, [[Done is better than perfect]], and I implemented it. It's better than when I didn't move my hand and worried about it.
    - I don't care about the issue of the link string not being an exact match because I can use a vector search.
    - It's cached line by line.
        - So if you add one line to a large page, only one line is translated.
    - Maintain indentation and line-by-line translation because of bullet points
        - I'm separating the indentation from the text before translating.
        - So different indentation of the same content is a cache hit.
    - Local language judgment is applied and lines that are not Japanese are passed through without translation.
        - This means that source code, image notation, etc. are no longer eligible for translation.
    - When you find a mistranslation, you can use your hand to correct the cache.
- I have no idea what the view is.
    - You're not even thinking about it?
    - They're on Github in text format.

2023-03-30
- It was rather rubbish with errors and I didn't put a retry on, so I haven't finished it yet.
    - I kept retrying with weird queries and risked wasting money, so until I knew it was okay, I'd just eyeball the error and retry manually.
- [https://github.com/meganii/sandbox-github-actions-scheduler](https://github.com/meganii/sandbox-github-actions-scheduler)
    - I'm referring to the
- [https://github.com/nishio/etude-github-actions](https://github.com/nishio/etude-github-actions)
    - It smells like...
    - We haven't run it through Github Action yet.
- > [@TwitterDev](https://twitter.com/TwitterDev/status/1641222782594990080): Today we are launching our new Twitter API access tiers! We’re excited to share more details about our self-serve access. 🧵
    - Good timing! I want to "translate my Scrapbox into English once a day and then have GPT tweet a summary in English.

- langdetect seems like a good idea to stop.
    - There are many misjudgments for short sentences, and because of probabilistic behavior, there are cases where "once we judged it to be English, but this time we judged it to be Japanese, so we translated it".
        - [https://github.com/nishio/etude-github-actions/commit/e86ca8e8119c492c72c4c1e58982b7830924c85b#diff-7bd0b7387ba890dfb8a3302f1795f74db56eba845bdd467f9c47f04717bab873](https://github.com/nishio/etude-github-actions/commit/e86ca8e8119c492c72c4c1e58982b7830924c85b#diff-7bd0b7387ba890dfb8a3302f1795f74db56eba845bdd467f9c47f04717bab873)
        - Like this, I'd say, "I think `#Amanojaku #Devil's Advocate` is English," and then leak a one-line translation.
        - Q: If I put in the full text, won't it be judged correctly? A: Yes, and it will also translate all the source code without Japanese that is placed on the page with the Japanese explanation.
    - If it contains even one character in the Japanese domain, it should be judged as Japanese.


[https://www.deepl.com/account/usage](https://www.deepl.com/account/usage)
- ![image](https://gyazo.com/a40aa315dd34aa7c9ada756b0bfb545a/thumb/1000)
- Now this should be about half way there in terms of page count, so it's surprisingly inexpensive, right? I guess.

2023/4/1
- Successfully completed.
- ![image](https://gyazo.com/796feeeb47fc4b9e3ddcbe3627ec60b0/thumb/1000)
- 23,000 yen. Quite a bit cheaper than expected.
    - I was going to estimate it at $70,000 in bytes, but apparently it's a Unicode character.
    - 13,115,848 characters / 27,493,421bytes
    - The number of characters was reduced from 13M to 9.3M due to the removal of indentation and line breaks and the removal of duplicate strings in the cache.

First, we turn zeros into ones, then we improve them.
- Where to place the translated
    - → For now, it's on Github.
        - →How to show what has been translated
            - [https://github.com/nishio/etude-github-actions/blob/main/nishio/pages_en/59280ec2ba093700118f9bc5.json](https://github.com/nishio/etude-github-actions/blob/main/nishio/pages_en/59280ec2ba093700118f9bc5.json)
            - I wondered why it was red, but it's a scrapbox with a json extension.
            - Can be read on Github if it can be converted to Markdown
            - But I think it's a bone of contention to make the link connect in a Scrapbox-like way.
            - Can [[mem.nhiro.org]] be loaded from Github?
- How to translate documents that are updated daily
    - Let's try to update it with Github Actions.
    - Time measurement at hand
        - `python main.py  2578.84s user 270.36s system 98% cpu 48:27.16 total`
        - What's taking so long?
        - Ah, updating the cache.
        - Fixed [Github](https://github.com/nishio/etude-github-actions/commit/98ac9d7e2267f3bc7faf2c02720c7d00bb7638b2)
            - `python main.py  3.73s user 2.56s system 68% cpu 9.118 total`

Re-crawl for updates during the past week
- `python main.py  39.36s user 14.77s system 10% cpu 8:49.13 total`
retranslation
- `total 28492485 no_cache 156769 ratio 0.005502117488172758`
- `python main.py  48.04s user 7.02s system 3% cpu 24:02.17 total`
    - Most of the time waiting for translation APIs

Execute with Github Actions
- It's been an hour and it's not over.
- I'd love to find out in more detail where it's slow.
- I've got the page fetch and translation in one script, so I don't know which is the problem or what.
    - If acquisition is slow
        - I'm taking all of them. That's right.
            - The update date and time are known at the initial candidate stage, so just take the ones that have been updated.
            - For those for which you have administrative privileges, you can use the export API.
    - If translation is slow
        - Because you're waiting for the API response in series.

Took six hours and it's been cancelled.
- ![image](https://gyazo.com/7da36b796fac0b2cdaba26c2e1fe6ff1/thumb/1000)
- Logged.
- Crawl's done, and it's stopped in the process of translating.
- `  9%|▉         | 1368/14461 [00:00<00:07, 1831.53it/s]`
    - I would think it would be slower if the cache wasn't working...
- `Error: The operation was canceled.`

2023/4/5
- I suspected the cache might not be working, but it wasn't.
- I changed various debug outputs to check the situation, but for some reason it completed easily. Huh?
    - I realized after a night's sleep that maybe the progress display was incompatible with the irregular terminal operations and the Github Actions mechanism for capturing logs and showing them in real time on the web?

2023/4/6
- First, import automatically into Scrapbox.
    - Ideally, you should connect to [[mem.nhiro.org]], but you can start with an easy step
- I want to auto Tweet the activity digest.
    - First of all, "Output Tweet contents to a file" and "Tweet by a human being".

- [[Experiment 2023-04-06]]

from [/villagepump/2023/04/07](https://scrapbox.io/villagepump/2023/04/07)
- I'm disappointed to see the Scrapbox machine translation result and see that it is translated as "NISHIO Hirokazu" from the very beginning.
- I noticed the ChatGPT Plugin coming during my lunch break.
- Talk of improving translation has blown over.
- and if you don't make a note of it later, "Why did I stop?" it becomes "Why did I quit?

next [[pScrapboxAutoTrans2023-04-18]]

---
This page is auto-translated from [/nishio/pScrapboxAutoTrans2023-03-25](https://scrapbox.io/nishio/pScrapboxAutoTrans2023-03-25) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.