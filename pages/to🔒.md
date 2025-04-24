---
title: "to🔒"
---

UserScript that, when executed on a Scrapbox page, creates a page in a private project with a key in the title, and the earth symbol is a link to the original page.
![image](https://gyazo.com/ef344a8d007bee6b11d949c2278d0d88/thumb/1000)

script.js

```javascript
const privateProject = "..."
scrapbox.PageMenu.addItem({
  title: 'to🔒',
  onClick: () => {
	const title = document.location.pathname.split("/")[2];
	window.open(`https://scrapbox.io/${privateProject}/🔒${title}`, "_blank")
  }
})
scrapbox.PageMenu.addItem({
  title: 'make🔒',
  onClick: () => {
	const title = document.location.pathname.split("/")[2];
	const body = `[https://scrapbox.io/nishio/${title} 🌏] [${title}]`
	window.open(`https://scrapbox.io/${privateProject}/🔒${title}?body=${body}`, "_blank")
  }
})
```


---
This page is auto-translated from [/nishio/to🔒](https://scrapbox.io/nishio/to🔒) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.