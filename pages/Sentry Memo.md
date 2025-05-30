---
title: "Sentry Memo"
---

from [[Sentry]]

2021-02-08
Sentry Memo
- [Create a Sentry Project | Sentry Documentation](https://docs.sentry.io/product/sentry-basics/guides/integrate-frontend/create-new-project/)
    - platform: React, name: keicho-webclient
    - `$ npm install --save @sentry/react @sentry/tracing`
    - > Next, import and initialize the Sentry module as early as possible, before initializing React:
ts

```typescript
import React from "react";
import ReactDOM from "react-dom";
import * as Sentry from "@sentry/react";
import { Integrations } from "@sentry/tracing";
import App from "./App";

Sentry.init({
  dsn: "https://*****.ingest.sentry.io/5627136",
  integrations: [new Integrations.BrowserTracing()],

  // We recommend adjusting this value in production, or using tracesSampler
  // for finer control
  tracesSampleRate: 1.0,
});

ReactDOM.render(<App />, document.getElementById("root"));
```

    - > The above configuration captures both error and performance data. To reduce the volume of performance data captured, change tracesSampleRate to a value between 0 and 1.
- I'll try to reproduce the error I made the other day intentionally.
ts

```typescript
// @ts-ignore
console.log([][0].TalkID);
```

    - ![image](https://gyazo.com/f3941c8b5f0b4a9ef3fc5900a8e0be19/thumb/1000)
    - ![image](https://gyazo.com/3b94acb65985631e3c423394a6f06b4d/thumb/1000)
    - I'm on a development server and I get an email saying `New alert from keicho-webclient in production
ts

```typescript
Sentry.init({ ...
  environment: process.env.NODE_ENV,
});
```



- [[Sentry to send out a User Feedback form in the event of an error]]
- [[Performance Measurement with Sentry]]

Send additional information
- `Sentry.setContext("Info", { TalkID: TalkID });`
- ![image](https://gyazo.com/7d3f3633cd42fbe42aed83457fbc9a2c/thumb/1000)

Server side
`$ pip install --upgrade sentry-sdk`
Import and initialize the Sentry SDK early in your application's setup:
python

```
import sentry_sdk
sentry_sdk.init(
    "https://013cb069fe1841fb920fd5d7e369debc@o376998.ingest.sentry.io/5628690",
    traces_sample_rate=1.0
)
```

python

```
@app.route('/')
def root():
    1 / 0
    return "OK"
```


I want to make an error on my local server to see if reporting to Sentry is working, but in Flask's development mode, the error is caught and I get a debug screen.
- Remove FLASK_ENV=development once
- Conversely, with this on, errors are not reported on the local server, which is usually a good thing.
![image](https://gyazo.com/e3b3a605f78047bb9224c5b5783bed5c/thumb/1000)
- Send additional information
    - `sentry_sdk.set_context("info", {"talk": talk, "text": text})`


- [Setting Up Your Sentry Account | Sentry Documentation](https://docs.sentry.io/product/sentry-basics/guides/getting-started/)

---
This page is auto-translated from [/nishio/Sentry Memo](https://scrapbox.io/nishio/Sentry Memo) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.