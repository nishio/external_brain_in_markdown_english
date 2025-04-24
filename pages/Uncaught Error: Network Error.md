---
title: "Uncaught Error: Network Error"
---

![image](https://gyazo.com/e1b043d657fea88b8fb75f94f810873d/thumb/1000)

- I get net::ERR_INTERNET_DISCONNECTED in a no internet connection situation (I know this)
- I want to be able to use it offline so I don't die from errors.
- How do you handle errors?
    - Neither firebase.initializeApp nor firebase.firestore is a Promise
    - No firebase.initializeApp and firebase.firestore with try
- Error handling should be done on the React side.
    - [Error Boundaries – React](https://reactjs.org/docs/error-boundaries.html)
    - > componentDidCatch and getDerivedStateFromError: There are no Hook equivalents for these methods yet, but they will be added soon.
        - [Hooks FAQ – React](https://reactjs.org/docs/hooks-faq.html)
        - Can't do it in FC.
    - I solved the problem by creating class ErrorBoundary.
    - Now I'm simply console.logging with componentDidCatch.
        - In the future, you can connect to [[Sentry]] or something like that.

[[pKakidashi]]

---
This page is auto-translated from [/nishio/Uncaught Error: Network Error](https://scrapbox.io/nishio/Uncaught Error: Network Error) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.