---
title: "add watchlist"
---

from [/villagepump/2022/03/25](https://scrapbox.io/villagepump/2022/03/25)
<img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>
- Watchlist, I've left it there thinking I'm not sure how to add it, but maybe others are adding it automatically?
    - ![image](https://gyazo.com/1900d8686c0ba3730f12963b1048193e/thumb/1000)
        - I'll add it when I open people's Project.<img src='https://scrapbox.io/api/pages/villagepump/kuuote/icon' alt='/villagepump/kuuote.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/villagepump/blu3mo/icon' alt='/villagepump/blu3mo.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/villagepump/takker/icon' alt='/villagepump/takker.icon' height="19.5"/>
            - ![image](https://gyazo.com/a861d978005cf61506061bf247ab31c2/thumb/1000)

            - If not, is it a bug?
            - Is it because it's Porter?<img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>
                - probable<img src='https://scrapbox.io/api/pages/villagepump/kuuote/icon' alt='/villagepump/kuuote.icon' height="19.5"/>
            - I think I'm putting it in localStorage or something, but I wonder if I can add a Porter to it in some clever way.<img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>
                - It doesn't have to be automatic, it could be manual.
            - Can be added with UserScript<img src='https://scrapbox.io/api/pages/villagepump/takker/icon' alt='/villagepump/takker.icon' height="19.5"/>
                - For example, [/takker/remote watch list#61c291b71280f00000f6d645](https://scrapbox.io/takker/remote watch list#61c291b71280f00000f6d645) will add about 1000 projects in `list.js` to the watch list
                    - Oh, `list.js` included private projects.
                        - I'll probably only put in a few things I know and try them out so I'm good to go.<img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>


[/takker/remote watch list](https://scrapbox.io/takker/remote watch list)

script.js

```javascript
const projectIds = [
'5e6cbe2d71038b00178729b1', // /sta stakiran institute
'5ad2d6b60268550014c2d723', // /rashitamemo Tadanori Kurashita's Idea Studio
'57ba889cc59c3e0f00979915', // /shokai hashimoto shokai
'60d84407e00111001ca49f7b', // /blu3mo-public bluemo-public
'5ad25639fcbd1b0014f970fb', // /dai-yamamoto dai-yamamoto
'5844e6b756624e0011d8e6c2', // /daiiz daiiz
'5b2b0eebb7bd41001461d2f4', // /halsk Hal Seki's Scrapbox
'5f260ed82c98a7001eddd442', // /issac-37765679 issac's Scrapbox
'5886ce9301cee80011d205a8', // /june29 29box
'58c9deee4dd2070011214160', // /kimiyuki Memo read by future self
'583dc452ebcbae0011e236ce', // /masui Toshiyuki Masui
'59fb2112121207900012774b18', // /motoso base element
'5ae7fecf7766b7001455cbd4', // /mtane0412 pumping thought latrine
'5f1810a1592883001eacf6b4', // /noratetsu Noratetsu's Room (Noratetsu Institute)
'5c6f5ba148eb0400174a245a', // /nwtgck nwtgck / Ryo Ota
'5f2f02f3c4a48d00237e1534', // /takker kutakutajuyon
'60648a9d02a598001c91685e', // /takoeight0821 Scrapbox of the stars
'5b6cd7c5e5da53001413f00e', // /taskmanagement taskmanagement scrapbox
'5f112854fd61a2001e36f78e', // /tkgshn tkgshn
'5983f25ce54f440011c2cd40', // /yamanoku yamaScrapbox
'60296e715a38ec001c5f1909', // /yosider yosider
'6016a310e41b6a0021bd81fa', // /hanadev
'5b8aa7cc1a07780014f61b7a', // /sudow
]
```


/hanadev
/sudow
- How do I find out the ID if I want to add a project that is not on the list?
    - [/scrapboxlab/api/projects/:projectname](https://scrapbox.io/scrapboxlab/api/projects/:projectname)を使います<img src='https://scrapbox.io/api/pages/villagepump/takker/icon' alt='/villagepump/takker.icon' height="19.5"/>

script.js

```javascript
function syncWatchList(projectIds) {
  // Do not overwrite existing watchList
  const projectsLastAccessed = JSON.parse(localStorage.getItem('projectsLastAccessed'));
  projectIds.forEach(id => projectsLastAccessed[id] ??= 0);
  localStorage.setItem('projectsLastAccessed', JSON.stringify(projectsLastAccessed));
}
syncWatchList(projectIds);
console.log("add watchlist")
```


- It didn't work.
    - I wonder if there is no localStorage in the browser in Porter or something...

---
This page is auto-translated from [/nishio/add watchlist](https://scrapbox.io/nishio/add watchlist) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.