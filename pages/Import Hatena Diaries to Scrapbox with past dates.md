---
title: "Import Hatena Diaries to Scrapbox with past dates"
---

from  [[Machine writes in Scrapbox]]

Objective.
- When I search for Scrapbox, I don't get any hits on past blog posts, I think I should get a hit.
- It's automatically converted to Hatena blog, but I'm not paying for it, so I get ads.
    - I feel bad when I link them.
- I want to bracket past articles as well.

2021-05-04 [[Hatena Diary]] imported into Scrapbox with past date [script](https://github.com/nishio/scbot/blob/main/from_hatena.py)
2021-12-20
- Q: It's been six months.
- A: Very good
        - [[Importing past blog posts into Scrapbox, six months, very good.]]

In the past (2018) I had even created a "script to convert exported XML to JSON in Scrapbox format".
    - [[Importing Hatena Diary into Scrapbox]]
- Why haven't you imported it into this project?
- Formatting is not fully supported.
- I didn't want the top of the page to be filled with mechanical articles.
    - → I noticed that if you put the update date in the past, the top page won't be filled.

(computer) format
- It looks like the entity reference `&gt;` is being erased when I read it in bs4.
    - I don't think that's possible, but something lost came up and I'm not sure how to solve it.
    - It's not a big deal, so I parsed it on my own.
- No conversion from Hatena notation to Scrapbox notation
    - I put it all together and put it in Scrapbox code notation.
    - If it hits the search and you can read it, that's all that matters.
    - Do `html.unescape
    - I was going to use the title of the blog as the page title, but decided against it because I felt it wasn't necessary.
        - All titles will be machine generated.
            - Easy mechanical removal if you decide it's not good enough after import
                - Q: Wouldn't it be better to make a backup before importing?
                    - A: If I want to undo the import after running the import for a while and editing various pages, I can't restore from a backup.
            - Safe and secure override operation
                - It's sad when a script is updated and reconverted and then overwritten and the human-written text is lost.
                - This anxiety prevents us from "keeping it updated".
                - Don't change the machine-generated page, just create a page with a good title that can be duplicated when you want to change it.
- ![image](https://gyazo.com/64bf2d44ad71f4b8515f6e6016d98f67/thumb/1000)
    - The creation date and time are correctly set to three years ago.
    - But, well, it might have been enough to just say "not on the top page" without having to match the exact date and time of creation.
python

```
def timestamp(*args):
    return datetime.datetime(*map(int, args)).timestamp()
```

    - 2021-06-29 PS: I still prefer the current "date and time the article was actually written" because I'm comfortable with the search results being in chronological order.

search (e.g. for someone using a search engine)
- ![image](https://gyazo.com/e3626a3f075a86a8838aa67c3723f9d4/thumb/1000)

I made a heading page but deleted it because I knew I would never use it.
- ![image](https://gyazo.com/8f7f138a86ffc2610f8e703406b0ec5e/thumb/1000)![image](https://gyazo.com/a8cacff7f08c9b94a2ca9755746640fe/thumb/1000)
    - [[Tasteless list]] is not good.


scale
- 120,000 lines of XML
- 220,000 lines of JSON
- 1500 pages

superscription
- Schedule: Can be overwritten if the change date/time has not changed.
- Schedule: Check for conflicts on import
- Actual: Always overwritable

Try it on an empty project
- It has to be admin.

Will bots be able to script their participation in the project as well?
:

```
Request URL: "https://scrapbox.io/api/projects/{project}/invitations/{key}"
POST
```


---
This page is auto-translated from [/nishio/はてなダイアリーを過去の日付でScrapboxにインポート](https://scrapbox.io/nishio/はてなダイアリーを過去の日付でScrapboxにインポート) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.