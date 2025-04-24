---
title: "Twitter Cards"
---

[Start using your card - Twitter Developers](https://developer.twitter.com/ja/docs/tweets/optimize-with-cards/guides/getting-started)
- How to combine with Open Graph tags is written at the end.
ts

```typescript
<meta name="twitter:card" content="summary" />
<meta name="twitter:creator" content="@nishio" />
<meta property="og:url" content="https://shinuwani.netlify.com/" />
<meta property="og:title" content="You who will die in ___ years" />
<meta property="og:description" content="I made this because I was watching the cartoon "The Crocodile Who Dies in 100 Days" and was wondering how long I would be dead." />
<meta property="og:image" content="https://shinuwani.netlify.com/shinuwani.jpg" />
```

- [Share Debugger - Facebook for Developers](https://developers.facebook.com/tools/debug/?q=https%3A%2F%2Fshinuwani.netlify.com%2F)
- [Card Validator | Twitter Developers](https://cards-dev.twitter.com/validator)


- Twitter Preview
    - ![image](https://gyazo.com/5b1094802c9149e4d37cf8cf46fc7552/thumb/1000)
- Real
    - ![image](https://gyazo.com/605989ee002c5ac2b889bbc79986f338/thumb/1000)



- Facebook Preview
    - ![image](https://gyazo.com/d4dd014e3710c224ce5c41dfaace9e1b/thumb/1000)
- Real
    - ![image](https://gyazo.com/a80db0cb4cc47f30c46d8a1c6ff4f85b/thumb/1000)

There was a suggestion to use [[react-helmet]], but we decided it was better to modify the head directly since it is a single file for a single page.

---
This page is auto-translated from [/nishio/Twitterカード](https://scrapbox.io/nishio/Twitterカード). If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.