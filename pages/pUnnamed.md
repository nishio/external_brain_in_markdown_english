---
title: "pUnnamed"
---

prev [[pScrapboxAutoTrans2023-03-25]]
- Decent within 3 weeks.
- What is sane?
    - The translation of "Yasukazu Nishio" on the self-introduction page is subtle.

- 2023/4/6
    - > Automatically import into Scrapbox first.
        - > Ideally, it would be good to connect to [[mem.nhiro.org]], but we'll start with an easy step.
    - > I want to Tweet activity digests automatically.
        - > First of all, "Output Tweet contents to a file" and "Tweet by a human being".
    - 4/7
    - > I'm disappointed to see the Scrapbox machine translation result and see that it is translated as "Yasukazu Nishio" from the very beginning.



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

- This issue translated as Yasukazu Nishio on the self-introduction page is subtle.
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


This page is auto-translated from [/nishio/pUnnamed](https://scrapbox.io/nishio/pUnnamed)