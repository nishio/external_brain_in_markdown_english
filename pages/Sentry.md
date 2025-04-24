---
title: "Sentry"
---

[[Sentry Memo]]


- [[Crash Report]]
[Application Monitoring and Error Tracking Software | Sentry](https://sentry.io/welcome/)

Getting Started - Docs
[https://docs.sentry.io/error-reporting/quickstart/?platform=browsernpm](https://docs.sentry.io/error-reporting/quickstart/?platform=browsernpm)

ts

```typescript
Sentry.init({
  dsn:
    "https://....ingest.sentry.io/...",
});
Sentry.captureMessage("Something went wrong"); 
```


js

```javascript
Sentry.configureScope(function(scope) {
  scope.setExtra("character_name", "Mighty Fighter");
});
```


> Be aware of maximum payload size - There are times, when you may want to send the whole application state as extra data. This is not recommended as application state can be very large and easily exceed the 200kB maximum that Sentry has on individual event payloads. When this happens, you’ll get an HTTP Error 413 Payload Too Large message as the server response or (when keepalive: true is set as fetch parameter), the request will stay in the pending state forever (eg. in Chrome).

![image](https://gyazo.com/f3d11ea932fa3d84bca24195fd619bd9/thumb/1000)
The mouse move is sending a lot of errors due to an embargo in the mouse down process. I wonder if it's possible to stop sending so many in a short period of time...

[Breadcrumbs - Docs](https://docs.sentry.io/enriching-error-data/breadcrumbs/?platform=browsernpm)

---
This page is auto-translated from [/nishio/Sentry](https://scrapbox.io/nishio/Sentry) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
sentry
Sentinel
- A value that does not appear in the real data, but is used exclusively to indicate the end of data
- Dummy data to be placed to reduce the number of condition judgments when there are multiple exit conditions for a loop processing input data.

[guard - Wikipedia](https://ja.wikipedia.org/wiki/%E7%95%AA%E5%85%B5)

---
This page is auto-translated from [/nishio/番兵](https://scrapbox.io/nishio/番兵) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.