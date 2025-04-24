---
title: "New tab after asynchronous processing"
---

![image](https://gyazo.com/87abc3ad250cdff7812402fb624702c2/thumb/1000)
- Select "Create New Map" from the menu to create a new map and open it in a new tab.
- However, this "Create New Map" is asynchronous because of the network involved, and Safari on the iPad blocks asynchronous new tabs without any notification to the user.
- As a result, only in Safari I get the "Huh? Why isn't it working? There's no error...".
- solution
    - There should be a notification that the process has started promptly after the user's operation.
    - So I'll give you a dialog.
    - Produce a button when completed.
        - Pop up in situations where pop ups are possible.
        - Safari silently squashes it, so the user explicitly presses the button

[[pRegroup-done-2020]]

---
This page is auto-translated from [/nishio/非同期処理の後の新規タブ](https://scrapbox.io/nishio/非同期処理の後の新規タブ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.