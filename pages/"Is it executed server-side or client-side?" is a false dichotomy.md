---
title: '"Is it executed server-side or client-side?" is a false dichotomy'
---

Next.js properly switches between server-side and client-side execution. However, if you write code that involves reading and writing Firestore without understanding the switch, you may face unexpected problems.<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>
- The appeal of Next.js is that it allows you to write both client-side and server-side code in the same language. The premise, however, is that a human being understands exactly what part of the code is to be executed where.

I don't know, so I asked GPT4.[[blind spot]] がわかった、なるほど両方で実行される部分があるのか<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
- > 1: Anything in getServerSideProps or getInitialProps runs on the server-side. These functions are used for server-side rendering. They are run on the server when a request is made to the page.
- > 2: Anything in getStaticProps or getStaticPaths also runs on the server-side. These functions are used for static generation. They are run at build time on the server.
- > 3: Any other code in your React components, outside the above functions, will run on both server and client side.
- > 4: Code in useEffect hooks runs on the client-side only.
- > 5:  Code in event handlers (like onClick, onSubmit, etc.) runs on the client-side only.

"Is it executed server-side or client-side?" is [[False dichotomy]].

When I used to use raw React, I used to write the Firebase initialization code in a module and import and use it in various places to ensure that the initialization code was running once before the call.
- The raw React runs entirely client-side, so there was no problem.
- I did the same thing this time and got an error message that there was no `window` in the initialization of `getAnalytics`.
    - I saw this error and thought "it's running on the server side".
    - From there, I mistakenly thought it wasn't "running client-side".
    - Stuck in a "false dichotomy."
- Stuck in the "false dichotomy" and unaware that my premise was out of whack, I told GPT, "I want to ensure that this initialization code is executed client-side."
    - When I did that, it started generating code to setState the module with dynamic import in useEffect.
    - Sure, that would only work on the client side, but "No, isn't that a quirky design?" I thought, "No, it's not right.
    - Here, I suspected an error in my understanding.
- GPT4 is useful, but if you communicate an inappropriate request with incorrect understanding, it generates complex code to try to manage the request
    - There is no way that "dynamic import in useEffect" is mandatory for the combination of Next.js and Firestore, which is so widely used that GPT4 can be generated.

In this case, there is no need to call `getAnalytics` in the initialization
- Call them where you need them.
- There was no need to write tricky code at all.

---
This page is auto-translated from [/nishio/「サーバサイドとクライアントサイドのどっちで実行される？」は誤った二分法](https://scrapbox.io/nishio/「サーバサイドとクライアントサイドのどっちで実行される？」は誤った二分法) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.