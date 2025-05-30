---
title: "Extracted UserScript"
---

2021-08-04
- I was reminded of this when you mentioned it.
    - [https://twitter.com/dedededalus/status/1422578181870014467?s=21](https://twitter.com/dedededalus/status/1422578181870014467?s=21)
- [[ScrapboxSRS]]
- SRS is Spaced Repetition System, a system that assists in reading back at gradually growing intervals. It is like a page that has not been updated for a long period of time surfacing occasionally to create an opportunity to look back at it.
- I haven't continued to use it.
- In retrospect, I'm not sure it was necessary to provide too many short-term links for the purpose of "creating an opportunity for old pages to surface and be looked back on from time to time.
    - A good theory is "[[On this day n years ago]]."
- If you want to rebuild it.
    - A few items are displayed in each of the following three categories: "100 days ago," "1 year ago," and "several years ago."
    - I'll make an improved version between meetings on Friday.

---

2018-06-22
- Cut out a section of a page in citation format on a new page
- The original page is not edited.
- Put a line permalink from the new page to the original page.
I want to make a

Will the original page be edited?
- Can it be edited?

What can be done with this
- [[Incremental Reading with Scrapbox]]

I couldn't figure out how to make a line permalink, but [[window.scrapbox.Page]] lines has a set of permalinks and text

Is the current New Page feature not good enough? Why not?
    - [[Humans are resistant to deletion.]]
- Deletion and editing can be done with the reassurance that the original text is still there.
- So the original text must be untouched.

- [[Scrapbox and long form]]


script.js

```javascript
function clip(text){
debugger;
      const lines = text.split(/[\r\n]/g)
      const title = lines[0]
        .trim()
        .replace(/\[[^\]]+.icon\]/gm, '')
        .replace(/[\[\]]/g, '')
      const projectRoot = (() => {
        const tmp = location.href.split('/')
        tmp.pop()
        return tmp.join('/')
      })()
      const currentPageTitle = decodeURIComponent(location.href.split(/\//g).pop())
      lines.unshift(`from [${currentPageTitle}]`)
      const body = encodeURIComponent(lines.join('\n'))
      window.open(`${projectRoot}/Re:${currentPageTitle}?body=${body}`)
      return text
}
scrapbox.PopupMenu.addButton({title: 'Clip', onClick: clip})

```



js

```javascript
  scrapbox.PopupMenu.addButton({
    title: 'NewPage2',
    onClick: text => {
      const lines = text.split(/[\r\n]/g)
      const title = lines[0]
        .trim()
        .replace(/\[[^\]]+.icon\]/gm, '')
        .replace(/[\[\]]/g, '')
      const projectRoot = (() => {
        const tmp = location.href.split('/')
        tmp.pop()
        return tmp.join('/')
      })()
      const currentPageTitle = decodeURIComponent(location.href.split(/\//g).pop())
      lines.unshift(`from [${currentPageTitle}]`)
      const body = encodeURIComponent(lines.join('\n'))
      window.open(`${projectRoot}/${title}?body=${body}`)
      return `[${title}]`
    }
  })
```


js

```javascript
const sortMode = 'log' // Interval Iteration Method
let visibleRankNum = 100; // ignored except for log
const day = 60 * 60 * 24 * 1000
const year = day * 365
let projectPages;

function get_data(){
  let xhr = new XMLHttpRequest()
  xhr.open('GET', `/api/pages/${scrapbox.Project.name}?limit=10000`)
  xhr.onload = (e) => {
    projectPages = JSON.parse(xhr.responseText).pages
    sort_pages()
    update_list()
  }
  xhr.send(null)
}

function sort_pages(){
  const now = Date.now()
  projectPages.forEach((page, index, pages) => {
    let diff = now - page['updated'] * 1000
    if(diff > 10 * day){
      page['score'] = (Math.log(diff / (10 * day)) / Math.log(2)) % 1
      page['ago'] = Math.floor(diff / day)
    }
  })
  projectPages = projectPages.filter(page => (page['score'] != null))
  projectPages.sort((a, b) => (a['score'] - b['score']))
}

function create_page(title, lines){
  const projectRoot = (() => {
    const tmp = location.href.split('/')
    tmp.pop()
    return tmp.join('/')
  })()
  const body = encodeURIComponent(lines.join('\n'))
  window.open(`${projectRoot}/${title}?body=${body}`)
}

function update_list(){
  scrapbox.PageMenu('Scrapbox Sort').removeAllItems()
  let page_lists = [];
  for (let i = 0; i < visibleRankNum; i++) {
    let page = projectPages[i]
    if(page == null) break;
    page_lists.push(`${strftime(new Date(page.updated * 1000))}(${page['ago']}) [${page['title']}]`)
  }
  create_page("SRS" + new Date().toISOString().slice(0, 19), page_lists)
}

function pad(number) {
  if (number < 10) {
    return '0' + number;
  }
  return number;
}

function strftime(d){
  return (
    d.getUTCFullYear() +
    '-' + pad(d.getUTCMonth() + 1) +
    '-' + pad(d.getUTCDate())
  )
}
scrapbox.PageMenu.addMenu({
  title: 'Scrapbox SRS2',
  image: 'https://gyazo.com/11140c8b35b407c5d490a94ec6f2528f/raw',
  onClick: () => {
    scrapbox.PageMenu('Scrapbox SRS').addItem({ title: 'Please wait...', image: null, onClick: () => null })
    get_data();
    scrapbox.PageMenu('Scrapbox Sort').removeAllItems()
  }
})
```


---
This page is auto-translated from [/nishio/抜き書きUserScript](https://scrapbox.io/nishio/抜き書きUserScript) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.