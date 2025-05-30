---
title: "Open Graph Image as a Service"
---

[https://og-image.vercel.app/](https://og-image.vercel.app/)

I'm giving Puppeteer the HTML and taking screenshots.
- We have to wait for that HTML to access the Firestore to read and render the data.
- Since access to the Firestore runs asynchronously after loading, there is no way to wait for it...
    - [https://pptr.dev/#?product=Puppeteer&version=v10.2.0&show=api-pagesetcontenthtml-options](https://pptr.dev/#?product=Puppeteer&version=v10.2.0&show=api-pagesetcontenthtml-options)
        - Option on the Puppeteer side to wait until all network connections stop.

- I'm generating HTML as a string and setContent.
    - This is going to be tough to connect with Kozaneba.
    - Seems like a good idea to separate it as a service and do it in GOTO.

- Even if the meta tags of a page are configured to be rewritten by JS after page load, crawlers of various social networking services cannot handle it.
- You have to serve HTML on the server side.
- I can use vercel to create minimal HTML with individual meta's on the server side and spit it out...

cache control
- [https://vercel.com/docs/edge-network/caching](https://vercel.com/docs/edge-network/caching)
- [https://vercel.com/docs/serverless-functions/edge-caching](https://vercel.com/docs/serverless-functions/edge-caching)

---
This page is auto-translated from [/nishio/Open Graph Image as a Service](https://scrapbox.io/nishio/Open Graph Image as a Service) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.