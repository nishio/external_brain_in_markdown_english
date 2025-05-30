---
title: "ToMyProj"
---

User script to extract the original text without destroying it
- Originally created "to copy and organize the content written in other projects into your own project.
    - So the source link and icon are supposed to be the name of the project.
- 2022-11-25 I've been using it for a while and found it useful within the same project
    - The current official "New Page" functionality changes the content of the original page.
    - So the psychological hurdle is high, as you have to use it while worrying about whether the change will have a negative impact.
    - It would be less painful to extract the "original page unchanged" once, organize it, and then consider whether to erase or modify the description of the original page.

2022-01-19
When you duplicate another project's description in your own project
- Make the icon a reference to the original project so that it is not broken
- Insert source link

turn out like this
    - [[Wellhead 2022-01-17]] Title tweaked.
    - Whether the link in the project should be a link to the original project...
        - We're not going to be able to connect with anything on this side of the project.
            - [[should not do]]
            - If there is a page with the same name in our project, it should be connected.
            - Not connected = not in this project" is also informative
                    - [[Notice the blanks.]]
            - If you think you need it at the cost of making it, make it, and if not so much, leave it alone.
2022-02-01
- The reference to icons of other projects from the well is broken.
- The title is "Re:", but the diary page was duplicated by mistake because the title was corrected after the fact
    - Well, but do you want to revise the title on the rest of the page?
    - Well, I can notice it because the link connects.
- Maybe the link to /nishio could be mechanically reverted to a link in the project.
2022-03-26
- You don't necessarily want to make a page.
    - For example, when adding a reference to an existing page in another project for that page
    - So I put it in the clipboard and then asked if I could create a page.

ToMyProj
script.js

```javascript
scrapbox.PopupMenu.addButton({
  title: 'ToMyProj',
  onClick: text => {
    const dst = 'nishio'
    const src = scrapbox.Project.name
    const new_text = text.replace(/\[([^\]\/]+).icon\]/gm, `[/${src}/$1.icon]`)

    const lines = new_text.split(/[\r\n]/g)

    const title = scrapbox.Page.title
    lines.unshift(`from [/${src}/${title}]`)

	const title_url = encodeURIComponent(title)
    const body = lines.join('\n')
    navigator.clipboard.writeText(body).then(()=>{
      if (window.confirm("copied. create page?")) {
        const body_enc = encodeURIComponent(body)
        window.open(`https://scrapbox.io/${dst}/Re:${title_url}?body=${body_enc}`)
      }
    })
  },
})
```


---
This page is auto-translated from [/nishio/ToMyProj](https://scrapbox.io/nishio/ToMyProj) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.