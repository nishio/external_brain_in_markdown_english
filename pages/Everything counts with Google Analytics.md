---
title: "Everything counts with Google Analytics"
---

I would like to know how many people have done a particular operation.
When that operation is performed, you can call Google Analytics directly from the JavaScript program you wrote and record the event.

This function can be used in many elaborate ways, but if you simply want to count the number of times, this is all you need.
ts

```typescript
window.gtag("event", "harvest");
```

- The "harvest" part is an easy-to-understand event name that you have given yourself.
- I think JavaScript people can work without the `window.`
- This is what it looks like on the Engagement page of Google Analytics
    - ![image](https://gyazo.com/0f3b5eaacb1d22186e322fc505ecf513/thumb/1000)
- You can trace it back from there to see when and how much it was used.
    - ![image](https://gyazo.com/9e7c70fbee8a2144a28e47d6d1174a1d/thumb/1000)

---
detailed account
- This gtag function is defined in the code that you are instructed to paste into the HTML when you first set up Google Analytics
- dataLayer is just adding to the list.
- Maybe there's a system that periodically checks the contents of this list and sends it to the server.
html

```html
 <script async src="https://www.googletagmanager.com/gtag/js?id=G-GBX75RXXXX"></script>
 <script>
   window.dataLayer = window.dataLayer || [];
   function gtag() { dataLayer.push(arguments); }
   gtag('js', new Date());

   gtag('config', 'G-GBX75RXXXX');
 </script>    
```


Manual Description
- The third argument can be used to send a variety of additional information.
- I was confused, thinking something had to be set up properly, but if you just want to count the number of times, you can omit it.
- [Measuring Google Analytics Events | Universal Analytics for the Web (gtag.js)](https://developers.google.com/analytics/devguides/collection/gtagjs/events)
js

```javascript
gtag('event', <action>, {
  'event_category': <category>,
  'event_label': <label>,
  'value': <value>
});
```

- [gtag.js API Reference | Global Site Tags (gtag.js) | Google Developers](https://developers.google.com/gtagjs/reference/api#event)
js

```javascript
gtag('event', 'screen_view', {
  'app_name': 'myAppName',
  'screen_name': 'Home'
});
```


About adding properties
- I was confused because I thought a property was an "attribute", but it seems to be a Google Analytics term for a unit of information that summarizes information that can have multiple units directly under an account.
    - If you create a new web service, you can add properties to it.
    - ![image](https://gyazo.com/a1f2e39c513892511b0f8341f133a9dd/thumb/1000)
    - ![image](https://gyazo.com/932bd389d5d9f04268c7636ebb07a06e/thumb/1000)

TypeScript will generate an error if the type of gtag is unknown, so declare it as follows
index.ts

```typescript
declare global {
  interface Window {
    gtag: (
      a: string,
      b: string,
      c?: { event_category?: string; event_label?: string; value?: number }
    ) => unknown;
  }
}
```


---
I was confused as to whether I had to set up the event, but it looks like I don't have to.
![image](https://gyazo.com/5cec00ab37f339eebab2e2eb5ca25a8a/thumb/1000)

---
This page is auto-translated from [/nishio/Google Analyticsで何でもカウント](https://scrapbox.io/nishio/Google Analyticsで何でもカウント) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.