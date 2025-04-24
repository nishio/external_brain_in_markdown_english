---
title: "Server-side rendering"
---

[[server-side rendering]]、[[SSR]]
One of the web app design
The server must create and return HTML for each request.

This was commonplace in the days of [[CGI]] and "web application frameworks" such as [[Ruby on Rails]] and [[Django]].

Subsequently, "JavaScript libraries for UI construction" such as [[React]] and [[Vue.js]] were developed, enabling most of the content to be built client-side (on the user's browser).
The ultimate form of this design is to have the server return the same HTML for every request, with JavaScript used to switch what is displayed. [This is called a "single page application" ([[SPA]]).

Assuming this design, the server side only requires static hosting. This has led to the creation of many services that specialize in providing static hosting.

On the other hand, however, there remained a need to create HTML on the server side, for example, by supporting the [[Open Graph Protocol]]. Support for this is described by static hosting service providers as "providing server-side rendering capabilities.

[[ISR]] [[SSG]]


---
This page is auto-translated from [/nishio/サーバサイドレンダリング](https://scrapbox.io/nishio/サーバサイドレンダリング) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.