---
title: "Redirect for SPA in Netlify"
---

- In an application (SPA) that is made of a single index.html file, there are times when I want to pass parameters.
- If you put it in the path, it will go to a file that is not index.html.
    - I thought it was a hash or query parameter, which I could work around in the settings, but it would be too much trouble.
- With [[Netlify]], that configuration is just 4 lines in netlify.toml in the root of the project
netlify.toml

```toml
[[redirects]]
  from = "/*"
  to = "/index.html"
  status = 200
```


- Someone did "write a webpack configuration to put _redirect in build..." but it's not necessary.
- [[Add to Home screen]]

---
This page is auto-translated from [/nishio/NetlifyでSPA用のリダイレクトをする](https://scrapbox.io/nishio/NetlifyでSPA用のリダイレクトをする) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.