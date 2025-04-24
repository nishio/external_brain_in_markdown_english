---
title: "Embed HTTPS services into other HTTPS services"
---

Conclusion.
- Impossible because the service I tried to embed was [[x-frame-options]]: SAMEORIGIN

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Which of the headers will tell me if I can embed a https service into another https service?
<img src='https://scrapbox.io/api/pages/nishio-en/o3-mini-high/icon' alt='o3-mini-high.icon' height="19.5"/>
Whether or not an HTTPS service can be embedded in another HTTPS service can be checked in the ### X-Frame-Options
 header (and possibly in the ### frame-ancestors
 directive in ### Content-Security-Policy
).
- X-Frame-Options:
    - If `DENY` or `SAMEORIGIN` is set, embedding on other sites is restricted.
- Content-Security-Policy (frame-ancestors):
    - More detailed control is possible.


---
This page is auto-translated from [/nishio/HTTPSサービスを他のHTTPSサービスに埋め込む](https://scrapbox.io/nishio/HTTPSサービスを他のHTTPSサービスに埋め込む) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.