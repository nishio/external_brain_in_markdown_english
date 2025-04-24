---
title: "pScrapboxAutoTrans2023-04-18"
---

old title: [[pUnnamed]]
prev [[pScrapboxAutoTrans2023-03-25]] ([[pScrapboxAutoTrans]] / [[ScrapboxAutoTrans]])
- Decent within 3 weeks.
- What is sane?
    - The translation of "NISHIO Hirokazu" on the self-introduction page is subtle.

- 2023/4/6
    - > Automatically import into Scrapbox first.
        - > Ideally, it would be good to connect to [[mem.nhiro.org]], but we'll start with an easy step.
    - > I want to Tweet activity digests automatically.
        - > First of all, "Output Tweet contents to a file" and "Tweet by a human being".
    - 4/7
    - > I'm disappointed to see the Scrapbox machine translation result and see that it is translated as "NISHIO Hirokazu" from the very beginning.



2023-04-20
- The case of the automatic import not working and leaving it alone.
- `ClientResponseError: 503, message='Service Unavailable', url=URL('https://scrapbox.io/api/page-data/import/nishio-en.json')`
    - I'm not sure what to do about it because I don't know the details.
    - This time it was "Is the problem that the JSON is too large?" and I narrowed it down to 100 entries, but got the same error.
- To begin with, the TS implementation of [[Scrapbox-Duplicator]] causes an error because the file size is too large.
:

```
% deno run --allow-net=scrapbox.io --allow-read=./ --allow-env import_to_scrapbox.ts
A new release of Deno is available: 1.32.2 → 1.32.4 Run `deno upgrade` to install it.
Importing 14726 pages to "/nishio-en"...
error: Uncaught (in promise) MulterError when importing pages: File too large
    const error = new Error();
                  ^
    at file:///Users/nishio/etude-github-actions/import_to_scrapbox.ts:31:19
```

- I narrowed it down to 100 cases and it worked.
:

```
% deno run --allow-net=scrapbox.io --allow-read=./ --allow-env import_to_scrapbox.ts
A new release of Deno is available: 1.32.2 → 1.32.5 Run `deno upgrade` to install it.
Importing 100 pages to "/nishio-en"...
import success! - 100 pages
```

- I can keep the data from the last update and only import the differences...
    - ✅

- This issue translated as NISHIO Hirokazu on the self-introduction page is subtle.
    - You could also put it in the glossary at DeepL
        - Better to do so in the future.
    - However, mistranslations in already-translated material are judged as "already translated, so you don't need to translate them", so they are not updated then.
    - So either way, the cache containing the mistranslation needs to be corrected or deleted.
        - Matches in string search were corrected with replace.
        - Maybe in the vast majority of cases this is the right thing to do.
    - ✅

Bring it up to a level where it is not embarrassing to show English speakers, "This is my Scrapbox.
- Once that's done, the next step is to merge vector search with GPT-4.
- Making my Scrapbox vector search available to everyone isn't quite as high a priority, is it?


When you were thinking about Scrapbox auto-translation before, there wasn't an inter-project link yet?
- I wondered how to map the English article to the Japanese article, but I thought, why not just add a link to the automatically translated page that says "Original page is here"? It turned out to be a good idea.
- ✅
    - I use the value of title when linking to a Japanese project, but then the link does not connect when it contains spaces, etc., so it is necessary to escape it correctly.

Yay, it's done!
- ![image](https://gyazo.com/a21ccd0e544bc2f7c9c609a3dfe439c9/thumb/1000)



> [@nishio](https://twitter.com/nishio/status/1649044721740967943?s=20): dead!
> >batch response: This repository is over its data quota. Account responsible for LFS bandwidth should purchase more data packs to restore access.
Ha, I'm running out of 1GB slots.
- At any rate, I charged $5/month and it looks like I'll get 50GB, so I did.
- ![image](https://gyazo.com/56893388970db00c70dfd786616fe94e/thumb/1000)

`Unlike a blog, the main [reader is myself]. It's ``Unlike a blog, the main [[reader is myself]].
- The page title is `reader is self`...

2023-04-21
- ![image](https://gyazo.com/73663a077af45b4c9f3a8e1907b48803/thumb/1000)
- The auto-run was successful.

2023-04-21
- from [/villagepump//nishio/pUnnamed(temporary)](https://scrapbox.io/villagepump//nishio/pUnnamed(temporary)).
    - [[ScrapboxTranslator]]では↓の方法で対処して上手く行きました（失敗ケースを観測していない）<img src='https://scrapbox.io/api/pages/villagepump/blu3mo/icon' alt='/villagepump/blu3mo.icon' height="19.5"/>
        1. translate all the titles into English first, and then create a table for Japanese-English correspondence
        2. mechanically replace links in the text with English
        3. throw a sentence whose link has already been replaced by English into ChatGPT and translate it
            - Not sure if this will work at DeepL
        - Oooh, that's helpful! >失敗ケースを観測していない<img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>

- A: len(cache) has 220,000
    - Since this is a dict, O(1)
        - It contains all lines, not just the title, but it's O(1), so we're not going to worry about it.
- B: Extract link notation
py

```
>>> re.findall("\[.*?\]", "aaa[bbb]ccc[ddd]eee")
['[bbb]', '[ddd]']
```

    - This would hit the contents of the code notation, but we're not going to worry about that.
- Find B from A and replace it if there is a translation

- Uh, "The Reader is Me" isn't even the page title to begin with.
    - ![image](https://gyazo.com/ac0ae1b0d459104876a5d618cb9c6911/thumb/1000)
    - This is the pattern.
- Links collected using `api/pages/nishio/search/titles`.
    - There are 25,000 cases.
    - I ran the translation for now.

2023-04-22
:

```
25321
100%|████████████████████████████████████████████████████████████████████████████████████████| 25321/25321 [4:37:38<00:00,  1.52it/s]
total 565897 no_cache 277634 ratio 0.4906087150135095
translate: 16659.303921374958
```


:

```
>[https://twitter.com/tkihira/status/1269780950105206787?s=21 @tkihira]: In [Weinberg]'s famous book "The Road to Super Engineer", he talks about how to face [temporary I remember it strongly as one of the most important stories in my own life.
['https://twitter.com/tkihira/status/1269780950105206787?s=21 @tkihira', 'Weinberg', 'temporary decline in competence']
>[https://twitter.com/tkihira/status/1269780950105206787?s=21 @tkihira]: In the famous book by [Weinberg] called "The Road to Super Engineer", he introduced a story about how to face [Temporary decline in competence] when learning a new technology, and it is strongly remembered as an important story in my mind.
```

It's luck whether you can translate it well or not.

In the meantime, I'm busy today and tomorrow, so I'll let this run.

2023/4/22
- Third idea
    - Remove the link notation from the line and translate it as plain text, and if the result contains "translated link content", convert it to a link, if not, append it to the end.

2023-04-23
:

```
%run translate.py
cache length: 229791
100%|████████████████████████████████████████████████████████████████████████████████████████| 14760/14760 [7:17:20<00:00,  1.78s/it]
total 29581111 no_cache 2492102 ratio 0.08424639628984862
translate: 26244.572622375097
```

Looks like they only had to retranslate about 8 percent.
- I wish I could quantitatively determine if it's getting better.

Import failed.
- ![image](https://gyazo.com/c8e644535d2db56c52756cdc39430dd9/thumb/1000)
- I redid it and it worked.
- mystery

2023-04-27
![image](https://gyazo.com/1292dbb0f3f52d08894785c58d8b4460/thumb/1000)
works well
[[Continuous Translation]]
next: [[pContinuousTranslation2023-04-27]]

---
This page is auto-translated from [/nishio/pScrapboxAutoTrans2023-04-18](https://scrapbox.io/nishio/pScrapboxAutoTrans2023-04-18) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.