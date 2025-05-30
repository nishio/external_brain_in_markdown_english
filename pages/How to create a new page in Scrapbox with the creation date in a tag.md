---
title: "How to create a new page in Scrapbox with the creation date in a tag"
---

You can create a bookmarklet with the following contents. Change "projname" in the code to the name of your project.
 javascript

```
javascript: var n = new Date(), ds = n.getFullYear() + "-" + (n.getMonth() < 9 ? "0" : "") + (n.getMonth() + 1) + "-" + (n.getDate() < 10 ? "0" : "") + n.getDate(), ts = n.getHours() + ":" + n.getMinutes() + ":" + n.getSeconds(); location.href="https://scrapbox.io/projname/" + ds + " " + ts + "?body=[" + ds + "] " + ts;
```


Since content can be specified with the GET parameter body of the URL when creating a new page, JavaScript is used to generate a string from the date and time and add it to the body.
At the moment "/projname/title/?body=..." method cannot create a page without a title, so the date is put in the title, but you may edit it as you see fit. If you leave the date title unedited, the page will be opened a second time. I don't have any plans to change it, because I think it's fine to keep "sentences so fragmented that they can't even be titled" together in date units.

---
PS: Current Scrapbox behavior is that if you try to create a new page titled 2017-04-09 using this API after changing the page titled 2017-04-09 to foo, it will redirect to foo and you will not be able to create the page. So I added the hour, minute, and second to the title, which works fine as long as you don't create the page twice a second.

[[2017-04-09]]
---
This page is auto-translated from [/nishio/Scrapboxで作成日付をタグに入れて新規ページ作成する方法](https://scrapbox.io/nishio/Scrapboxで作成日付をタグに入れて新規ページ作成する方法) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.