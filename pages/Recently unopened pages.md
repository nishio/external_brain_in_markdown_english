---
title: "Recently unopened pages"
---

from [/kuboon/open-recently](https://scrapbox.io/kuboon/open-recently).
script.js

```javascript
const title = 'Least Visited'
scrapbox.PageMenu.addMenu({
  title,
  image: 'https://i.gyazo.com/e71773a00dadd7bb6811206df59790c7.png',
  onClick: () => {
    if(scrapbox.PageMenu().menus.get(title).items.length === 0) addItems()
  }
});
async function addItems(){
  const proj = scrapbox.Project.name
  const pages = scrapbox.Project.pages.filter(x=>x.exists).length
  const count = 5
  const res = await fetch(`/api/pages/${proj}?sort=accessed&limit=${count}&skip=${pages-count}`).then(x=>x.json())
  const menu = scrapbox.PageMenu(title)
  //menu.removeAllItems()
  for(const page of res.pages){
    const { title } = page
    menu.addItem({
      title,
      onClick: () => location.href = `/${proj}/${encodeURIComponent(title)}`
    })
  }
  console.log(`${title} loaded`)
}
```


---
This page is auto-translated from [/nishio/最近開いてないページ](https://scrapbox.io/nishio/最近開いてないページ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.