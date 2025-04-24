---
title: "✅Image stickies are not showing up in the latest Chrome."
---

[[pRegroup-done]]
summary
- Chrome no longer reads HTTP images from HTTPS pages.
- The image needed to have its headers tweaked to resolve [[canvas pollution]], so it was passed through a proxy server set up in EC2, which was HTTP
- Moved server to heroku to solve the problem.
    - heroku is using a wildcard certificate for gunicorn.
    - It should be OK to get your own certificate and do it on EC2 with gunicorn in between.

---
phenomenon
- Image stickies are not displayed on PC
- Scrapbox sticky icon does not appear on my PC

reference
    - [[Display images on stickies]]
    - > I set up a proxy with EC2-nano.

This proxy is HTTP, but the latest Chrome no longer allows requests from HTTPS pages to HTTP
- `Mixed Content: The page at 'https://...' was loaded over HTTPS, but requested an insecure element 'http://...'. This request was automatically upgraded to HTTPS, For more information see`
- [Chromium Blog: No More Mixed Messages About HTTPS](https://blog.chromium.org/2019/10/no-more-mixed-messages-about-https.html)
    - > This feature will autoupgrade optionally-blockable mixed content (HTTP content in HTTPS sites) by rewriting the URL to HTTPS, without a fallback to HTTP if the content is not available over HTTPS. Image mixed content autoupgrades by default are targeted for M86.
    - The default for images used to be no auto-upgrade, but this has been changed since M86. This auto-upgrade does not fall back to HTTP, so images served only via HTTP will not be displayed.
    - → net::ERR_SSL_PROTOCOL_ERROR
- From Chrome M86
- [Enabling HTTPS on your server | Web | Google Developers](https://developers.google.com/web/fundamentals/security/encrypt-in-transit/enable-https)

solution plan
- HTTPS for servers written in Flask
    - [rest - can you add HTTPS functionality to a python flask web server? - Stack Overflow](https://stackoverflow.com/questions/29458548/can-you-add-https-functionality-to-a-python-flask-web-server)
- Other Methods
    - AWS Lambda, for example?
    - Put cloudflare in the foreground
- Why not Lambda?
        - [[Running image proxy with AWS Lambda]]
    - It was too much work to return the binary data.
- The API server I put on heroku is working fine, why?
    - It's across gunicorn, so HTTPS there.

---
This page is auto-translated from [/nishio/✅最新のChromeで画像付箋が表示されない](https://scrapbox.io/nishio/✅最新のChromeで画像付箋が表示されない) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.