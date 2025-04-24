---
title: "Python / FastAPI → TypeScript / Remix"
---

> [kenn](https://x.com/kenn/status/1773179207859732954) summer cleanup.
>
>  I made a decision to abandon the [[Python]] / [[FastAPI]] backend & monorepo that I've been gorging myself writing and maintaining for about 1.5 years, and completed the transition to a simple [[TypeScript]] / [[Remix]] full stack & monolith.
>
>  ・ The prediction at the beginning of 2023 that Python would be necessary for turning around proprietary AI models was off, and the necessary parts are now available simply by combining external services.
>
>  ・ During this period, I wrote both languages to deepen my understanding, and I concluded that TypeScript is superior in both language and ecosystem.
>
>  Above all, there is a limited choice of languages for writing UI, such as JS / Swift / Kotlin, and it is reasonable to unify with something close to them.
>
>  - ORM, which has always been a concern, is now very portable and secure after the migration from Prisma to Drizzle (I don't understand how you can think that SQLAlchemy is OK).
>
>  ・Jupyter Notebook was useful for manual script execution, but Node can do just as well or better if the REPL is implemented properly (although it is not suitable for ad hoc chart generation, etc.).
>
>  ・ External API calls that do not need to wait for completion, such as sending an email, can be fire-and-forget with setImmediate(async () => { await myJob() }), so job queues like Sidekiq are no longer necessary, making it even simpler.
>
>  ・The code has been dramatically simplified as a result, the black box feeling has almost disappeared, and we now have a sense that we have a grasp of the whole picture.
>
>  ・That has improved the overall quality of the product, and Sentry error notifications are seldom received, allowing us to squash them as soon as they come in and keep the basic zero status.
>
>  It was quite a challenge, but I think we can accelerate from here.
>
>  [https://x.com/kenn/status/1773179207859732954…](https://x.com/kenn/status/1773179207859732954…)

> [kenn](https://x.com/kenn/status/1825834094523207910) The advantage of JS/TS is that the server and client can use the same language. However, with the advent of Remix / RSC, which mixes server and client code in the same file, the lock-in to the JS ecosystem seems to be finally complete. Now GET -> Draw -> POST
>  ![image](https://pbs.twimg.com/media/GJuYPziaEAAvs0A?format=png&name=medium#.png)


> [kenn](https://x.com/kenn/status/1825925257502535839) But nowadays, with server environments like Render and Vercel that can be deployed with a single git commit, development support by LLM, and ultra-lightweight With full-stack frameworks like Remix, the threshold for web app development has dropped dramatically, so it's heaven for anyone who wants to make something.
>
>  On the other hand, it's hard for people who don't have anything they want to make, just technology.


---
This page is auto-translated from [/nishio/Python / FastAPI → TypeScript / Remix](https://scrapbox.io/nishio/Python / FastAPI → TypeScript / Remix) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.