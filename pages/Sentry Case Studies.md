---
title: "Sentry Case Studies"
---

Examples of what you will learn when you add Sentry

I'm getting about 6 errors like this on the server over time.
![image](https://gyazo.com/bbb616fcd3c678da5ccd62282bf754a4/thumb/1000)

![image](https://gyazo.com/410a167470483ba6a31ff1341ca2a339/thumb/1000)
py

```
def initialize(mode, env):
    for x in plugins:
        if mode == x.MODE:
            env.log.append([0, x.START_QUESTION])
            env.state = x.START
            return
    else:
        raise ValueError(f"unknown mode {mode}")
```


Ah, that's because you've made it so that the mode specification is received in the URL, so you get an error when there's garbage at the end of the URL.

I tried to make a decision with startswith instead of equal, and also to go into normal mode if I still couldn't make a decision.

---
This page is auto-translated from [/nishio/Sentryの事例](https://scrapbox.io/nishio/Sentryの事例) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.