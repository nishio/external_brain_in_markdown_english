---
title: "AskChatGPT"
---

![image](https://gyazo.com/f49c717d1e872e813335032f19b104fd/thumb/1000)


script.js

```javascript
 scrapbox.PopupMenu.addButton({
   title: "AskChatGPT",
   onClick: (text) => {
     alert(text);
     askChatGPT(text).then((x) => {
       const result = "[ChatGPT.icon]" + x.choices[0].message.content.trim();
       console.log(text + "\n" + result)
       window.chatgpt_result = result;
       alert(text + "\n" + result);
     });
   },
 });
 scrapbox.PopupMenu.addButton({
   title: "PasteChatGPT",
   onClick: (text) => {
     return window.chatgpt_result;
   },
 }); 
```



---
This page is auto-translated from [/nishio/AskChatGPT](https://scrapbox.io/nishio/AskChatGPT) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.