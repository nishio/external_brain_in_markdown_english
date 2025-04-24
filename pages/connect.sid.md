---
title: "connect.sid"
---

Authentication information to hit the API from scripts that require a Scrapbox login

Authentication information is set in the cookie while logged in with a browser. Use this.

This cookie is [[Secure]] and [[HttpOnly]], so it is not known by looking at document.cookie.
> To prevent cross-site scripting (XSS) attacks, HttpOnly cookies are inaccessible to JavaScript's Document.cookie API
- [HTTP cookies | MDN](https://developer.mozilla.org/en-US/docs/Web/HTTP/Cookies)

With Chrome Devtools, you can see it here.
- ![image](https://gyazo.com/ce08d69ca4712edf038c17fb9f8f2bd2/thumb/1000)

Specifically, the name "connect.sid" contains authentication information. For example, when calling the API with [[requests]], you can pass it as a cookie.
python

```
cookies={"connect.sid": "..."}
r = requests.get("https://scrapbox.io/api/pages/...", cookies=cookies) 
```


We need to be careful not to leak this information.
- If you leaked it, you can reset it by logging out and logging back in.
---
This page is auto-translated from [/nishio/connect.sid](https://scrapbox.io/nishio/connect.sid) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.