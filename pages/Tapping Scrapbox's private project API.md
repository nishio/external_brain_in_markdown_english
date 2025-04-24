---
title: "Tapping Scrapbox's private project API"
---

[[connect.sid]].
- I want to organize this as it is not limited to PRIVATE projects.
- But since it is linked to from many places, I decided to keep this page alive (2023-08-09).

2018-12-17
The API for public projects can get data by simply GETing it, but doing so in a private project will result in a 401. (No wonder).

When you access a private project while logged in, authentication information is set in a cookie. Use this.

This cookie is [[Secure]] and [[HttpOnly]], so it is not known by looking at document.cookie.
> To prevent cross-site scripting (XSS) attacks, HttpOnly cookies are inaccessible to JavaScript's Document.cookie API
- [HTTP cookies | MDN](https://developer.mozilla.org/en-US/docs/Web/HTTP/Cookies)

With Chrome Devtools, you can see it here.
- ![image](https://gyazo.com/ce08d69ca4712edf038c17fb9f8f2bd2/thumb/1000)

Specifically, the name "connect.sid" contains authentication information. This can be passed to [[requests]], for example.
python

```
cookies={"connect.sid": "..."}
r = requests.get("https://scrapbox.io/api/pages/...", cookies=cookies) 
```


This connect.sid is the one that doesn't expire until 2020 as of 2018, so we can access it for the time being.
We need to be careful because I don't know if there is a way to reset this information if it is inadvertently divulged.
- I logged out and logged back in and it was different.

thanks moriyoshi

[[ScrapboxAPI]] [[Scrapbox]]

---
This page is auto-translated from [/nishio/ScrapboxのprivateプロジェクトのAPIを叩く](https://scrapbox.io/nishio/ScrapboxのprivateプロジェクトのAPIを叩く) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.