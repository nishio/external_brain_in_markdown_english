---
title: "WebUI creation work memo"
---

Work to add WebUI to [pKeicho
    - [[WebUI creation work memo day 1]]

What to do next
- When a talk ID is specified, read it from Firebase and display the log.
- The conversation display part is fine as it is, the input fields are hidden, and the menu opens a dialog for advanced export.

- Parsing conversation IDs passed as hashes
    - [URLSearchParams - Web API | MDN](https://developer.mozilla.org/ja/docs/Web/API/URLSearchParams)

- If you just want to view the logs, you can read them directly from Firebase without going through the server.
    - `$ npm install firebase`
        - [[npm's --save]]
    - I get a type error with firebase@8
        - Not sure. @7.

- I was able to display the log.
    - [https://keicho.netlify.app/#talk=I9IlVW6Xt58NlNHAjdfq](https://keicho.netlify.app/#talk=I9IlVW6Xt58NlNHAjdfq)
    - Note: there is no way to get the URL for this log view after a human conversation, I'll add it later
- Next up is an export function for Regroup.

- Looks good with menu items and full screen dialog.
    - Material-UI's Menu has a warning in the latest React's StrictMode.
        - [[FIXED: Menu does not close in Material-UI]]
    - ![image](https://gyazo.com/1250d54f4717becec7fc6ff53b2f10c6/thumb/1000)
- Next to Full Screen Dialog
    - ![image](https://gyazo.com/164ee185463bfa29adafe6e89306c80e/thumb/1000)
    - ![image](https://gyazo.com/33382aa26072481d3b68a61b2e214982/thumb/1000)
- ![image](https://gyazo.com/e52316181ce2e614ef9a873c48da5cd0/thumb/1000)
- I pasted it into Regroup and then clicked on the line splitting, but since I was going to split everything anyway, I felt like if I hit export, it should split everything server-side and then import it into Regroup and open it.
- The current log object is broken up between extracted keywords and conversations, but it would be easier to organize them if they were arranged in chronological order.
    - It also picks up user "ask first" commands, etc., so it is kind to remove them when exporting.

> Note: there is no way to get the URL for this log view after a human conversation, I'll add it later
- I noticed how easy it was, so I added it to the menu.

I used it while taking a walk.
    - [[Conversation Log 20210121]]
- I chopped it up into 312 sticky notes, that's a bit much...
    - ![image](https://gyazo.com/634bfb47b5ea5d820c5e39eca46524b9/thumb/1000)
    - ![image](https://gyazo.com/bebc95b7f324a0b14fbfd9a755a035ac/thumb/1000)
    - Not much to go on.
    - So fundamentally, there's more than one story.

Export in Scrapbox format also implemented.

---
This page is auto-translated from [/nishio/WebUI作成作業メモ](https://scrapbox.io/nishio/WebUI作成作業メモ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.