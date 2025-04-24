---
title: "Create a new page by pressing the new line key"
---

- When not editing, create a new page by pressing the new line key.
- [/masui](https://scrapbox.io/masui)I got this from my teacher.
- convenient
script.js

```javascript
$('body').on('keydown',function(e){ // Enter key to create new page
   if(e.target.tagName != "TEXTAREA" && e.target.tagName != "INPUT"){
      if(e.key == 'Enter'){
         var project = location.href.split('/')[3];
         location.href = `/${project}/new`;
      }
   }
});
$('.btn.btn-default').on('click',function(){
   var s = $('.form-control').val();
   if(s == ''){
      var project = location.href.split('/')[3];
      location.href = `/${project}/new`;
   }
});
```



---
This page is auto-translated from [/nishio/改行キーで新規ページ作成](https://scrapbox.io/nishio/改行キーで新規ページ作成) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.