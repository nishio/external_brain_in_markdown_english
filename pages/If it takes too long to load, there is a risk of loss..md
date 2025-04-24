---
title: "If it takes too long to load, there is a risk of loss."
---

- ![image](https://gyazo.com/45f6f02cae08e863c916a4b47dd3ff1a/thumb/1000)

- In designing the app, I designed it as "the app has one map".
- We decided to create a map of the initial state when the app is launched.
- Subsequently, the following features were added
    - At startup, it reads information from the server and loads the data, if any.
    - Whenever there is a Map update, save it to the server.
- Usually the loading time is instantaneous, so it wasn't a problem.
- But after 6 hours of accumulating many people's drawings, it started to take a long time.
- Editing the initial state map before loading is complete writes its contents to the server

solution
- The "app has one map" is incorrect.
- App has a maximum of one map" is appropriate.
- The initial state of the application is "Do you want to create a new map? Open existing map?" It should be
    - The initial map is created only when you choose to create a new one.
- Those who opened the edit link directly chose "Open Existing Map" equivalent.
    - In this case, the loading indicator should be displayed until the loading is completed and editing should not be allowed.

Related: [[No editing unless explicitly in edit mode.]]
[[pRegroup2020]]

---
This page is auto-translated from [/nishio/ロードに時間が掛かると消失リスクがある](https://scrapbox.io/nishio/ロードに時間が掛かると消失リスクがある) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.