---
title: "I want to give a link when no hash is specified."
---

from [[pRegroup2020]]
I want to give a link when no hash is specified.
This didn't work (it also comes up when a hash is specified).
jsx

```
      <HashRouter>
        <Route path="/:id" component={Child} />

        {/* <Route exact path="/">
          <ul>
            <li>
              <a href="/#manual">Manual</a>
            </li>
            <li>
              <a href="/#key=sandbox">Sandbox</a>
            </li>
          </ul>
        </Route> */}

      </HashRouter>
```

[[HashRouter]]

---
This page is auto-translated from [/nishio/ハッシュが指定されていないときにリンクを出したい](https://scrapbox.io/nishio/ハッシュが指定されていないときにリンクを出したい) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.