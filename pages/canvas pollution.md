---
title: "canvas pollution"
---

I want to draw an image file on server A, which I do not control, in Canvas of a web application I am building, and export the edited result.

however
> If you draw any data loaded from another origin onto a canvas without permission from CORS, the canvas will be tainted. The tainted canvas will no longer be considered safe, and any attempt to retrieve image data from it will result in an exception.
- [https://developer.mozilla.org/ja/docs/Web/HTML/CORS_enabled_image](https://developer.mozilla.org/ja/docs/Web/HTML/CORS_enabled_image)

In fact, server A returns a header like this
- `access-control-allow-origin: https://gyazo.com`

therefore
- Set up your own proxy server B
- Throwing a request to B throws a request to A
- B returns its response header with Access-Control-Allow-Origin "*".
I thought of that.

Solution → [[Canvas Pollution Solution Edition]].

--- Below is a discussion of the past

I'm wondering if it's possible to do this B with Amazon CloudFront, or if there's something easy to use without having to implement it on my own, and since the only thing to proxy is images, and those images are not updated or anything, I'm wondering if it's possible to do it with a CDN-like thing.

If I set the origin server to A in CloudFront, I could access B to get A's content, but server A returns 301 Moved Permanently for accesses from domains other than its own.
![image](https://gyazo.com/848d5d2c53bf2b4818bf5567cff101ab/thumb/1000)

hmm
- AWS Lambda downloads and returns images from server A
- HTTP(S) mouth on this with API Gateway
- Cache it in CloudFront for about a year.
I wonder...

[[pRegroup2020-done]]

---
This page is auto-translated from [/nishio/キャンバス汚染](https://scrapbox.io/nishio/キャンバス汚染) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.