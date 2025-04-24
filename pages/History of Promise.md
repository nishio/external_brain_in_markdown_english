---
title: "History of Promise"
---

[The history of Promises](https://samsaccone.com/posts/history-of-promises.html)
- This person wrote a more than adequate and substantial commentary. Below is my summary and additions.

The Promise idea has its origins in an older
- [Future pattern - Wikipedia](https://ja.wikipedia.org/wiki/Future_パターン)
- [Futures and promises - Wikipedia](https://en.wikipedia.org/wiki/Futures_and_promises)

The 1997 E language is almost in the same form as Promise is today.
- [E (programming language) - Wikipedia](https://en.wikipedia.org/wiki/E_(programming_language))
Twisted, a network programming framework implemented in Python in 2001, was implemented with reference to the E language
- It was called Deferred.
- [Twisted - Wikipedia](https://ja.wikipedia.org/wiki/Twisted)

MochiKit, a lightweight JavaScript library, was implemented in 2005 with reference to Twisted
- at that time[XMLHttpRequest - Web APIs | MDN](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest)が使われていた、今のfetchに慣れた人からするとすごくめんどくさい<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
    - The intent was to make this easier.
- [MochiKit - Wikipedia](https://en.wikipedia.org/wiki/MochiKit)

Dojo, Q, and a number of other JavaScript libraries began to adopt similar concepts, and jQuery did so in 2010.
- [Dojo Toolkit - Wikipedia](https://ja.wikipedia.org/wiki/Dojo_Toolkit)
- [Q](https://github.com/kriskowal/q)
- jQuery was at least for a time a very major JavaScript library<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
    - The air of someone who doesn't know much about it and uses it anyway.
    - jQuery has allowed "this way of doing things" to spread to a wide range of JavaScript programmers.

A unified test case [Promises/A+](https://promisesaplus.com/) was created, and the mixed implementations of "this way of doing things" became "Promise implementations that behave the same".
- This also helped standardization by objectively demonstrating that a single concept of "Promise" is used in a wide range

It was then standardized in 2015 in the form of [[ES2015]].

- [[Proposed Technical Additions to Support Coding]]

---
This page is auto-translated from [/nishio/Promiseの歴史](https://scrapbox.io/nishio/Promiseの歴史) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.