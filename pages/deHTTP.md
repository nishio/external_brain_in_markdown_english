---
title: "deHTTP"
---

- [[Latest Chrome does not allow HTTP images to be displayed on HTTPS pages]]
- We need to do something about it.

I don't know what to do.
- Proposal to use other services
    - Advantages: Easy?
    - Disadvantage: You sometimes do more than just static delivery.
        - Maybe set up an API server that does a little natural language processing and returns...
    - [[Github Pages]].
        - The theory is that you don't need a server because you're just delivering the data statically anyway.
        - I've maintained that it's convenient to have a server when you want to do a little something, but you haven't done that in years, you'd rather use heroku or netlify.
    - Put [[Cloudflare]] in the front
        - Hmmm, it was mentioned on Chrome's blog, etc., but in a big way...
        - I guess that's as far as one can go with the free plan...
    - Shove all static-distributed images into Gyazo.
        - Theoretically, it's not impossible, but that's about it.
        - I need to go around and re-post the URL.
- Distribute with HTTPS on your own.
    - I'm probably at the level where Apache is probably running right now, so I'm just going to start looking into it.
    - If you're leaving it in that state, there could be a security issue or something, and since you're not maintaining it properly, shouldn't you avoid a situation where you have to maintain it yourself?

Do something that is not a static delivery.
- I didn't bother with [[pLinkSuggest]] or other typical examples, and when I looked into it, I found that I had deployed to [[heroku]] and it was HTTPS on its own.
    - Oh, I see, I was designing it according to the official manual to put [[gunicorn]] between the two, and this is where HTTPS comes in.
- This might be the easiest for this application...

---
This page is auto-translated from [/nishio/脱HTTP](https://scrapbox.io/nishio/脱HTTP) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.