---
title: "NEXT_PUBLIC_"
---

<img src='https://scrapbox.io/api/pages/nishio-en/o3-mini-high/icon' alt='o3-mini-high.icon' height="19.5"/>In front-end environments such as Next.js, process.env is embedded at build time, and not all environment variables are exposed to the client side for security reasons. Normally, only environment variables beginning with NEXT_PUBLIC_ are injected on the client side, so even if you do JSON.stringify(process.env) directly, it will be displayed as {} as per the specification.

---
This page is auto-translated from [/nishio/NEXT_PUBLIC_](https://scrapbox.io/nishio/NEXT_PUBLIC_) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.