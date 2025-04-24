---
title: "Add to Home screen"
---

- [[Add to Home Screen]], sometimes abbreviated as [A2HS
- [Add to Home screen - Progressive web apps (PWAs) | MDN](https://developer.mozilla.org/en-US/docs/Web/Progressive_web_apps/Add_to_home_screen)
- > To have a manifest file with the correct fields filled in, linked from the HTML head.
- If start_url is different for each person, manifest file needs to be created differently.
    - Using lambda seems like a good idea.
    - →If you are using [[Netlify]], you can use [[Netlify Functions]] to do it quickly.
        - [Function definition](https://github.com/nishio/kakidashi/blob/master/functions/makeManifest.js)
        - [plug](https://github.com/nishio/kakidashi/blob/20d7020d6c7f077b66ee976a3f9969b986f02e88/src/App.tsx#L117-L119) in [[react-helmet]]

#PWA

---
This page is auto-translated from [/nishio/Add to Home screen](https://scrapbox.io/nishio/Add to Home screen) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.