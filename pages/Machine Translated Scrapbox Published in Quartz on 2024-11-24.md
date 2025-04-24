---
title: "Machine Translated Scrapbox Published in Quartz on 2024-11-24"
---

from[/villagepump/machine-translated Scrapbox published in Quartz 2024-11-24](https://scrapbox.io/villagepump/machine-translated Scrapbox published in Quartz 2024-11-24)

Verbalize what you are trying to do.<img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>
- Automatic English translation from Scrapbox (Cosense) is now running on GitHub Action.
- But after translation, importing into Scrapbox is rubbing me the wrong way.
    - Sometimes this happens, but it's inexplicable, and it's kind of a pain in the ass now - I'm not going to import it into Scrapbox.
    - Discussion of [[import to /villagepump/Cosense mysteriously rubs me the wrong way]].
    - [[Obsidian Vault at Quartz]].
- There is an example of [[ScrapboxToObsidian]] converting Scrapbox JSON to Obsidian Markdown.
- Why don't we combine this and do "Scrapbox -> JSON -> English translation of JSON -> Markdown -> publish in Quartz"? I'm thinking.


[[Quartz]]はv4になって[[Preact]]ベースになったらしい<img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>
- Let's do a little research first.
- [Welcome to Quartz 4](https://quartz.jzhao.xyz/)
- I'll give it a shot anyway.
- Choose how to initialize the content in `/Users/nishio/quartz/content`
- │  Empty Quartz
- ◆  Choose how Quartz should resolve links in your content. This should match Obsidian's link format. You can change this later in `quartz.config.ts`.
- │  ● Treat links as shortest path ((default))
- │  ○ Treat links as absolute path
- │  ○ Treat links as relative paths
    - Hmmm, let's leave it at default.
- `$ npx quartz build --serve`
- Motion made.
Next survey
- [[ScrapboxToObsidian]]
- [/villagepump/nishio/from_scrapbox](https://scrapbox.io/villagepump/nishio/from_scrapbox)I found this
    - I've written a lot of stuff and even have uncommitted edits.
    - What's the situation here?
    - [[Static generation in Quartz from Markdown and serve in Github Pages]] I'm reading.
- Even then, Quartz looks v4.
- On the other hand, back then it was Scrapbox, not Cosense.
Quartz
- [https://github.com/nishio/quartz](https://github.com/nishio/quartz)
- `This branch is 3 commits ahead of, 564 commits behind jackyzha0/quartz:v4`
- Chaos because content updates are also in the same repository!
- `$ git pull --rebase upstream v4`
- > CONFLICT (content): Merge conflict in package-lock.json
- There are 564 commits, so I'm not sure what the big picture is.
- Are there separate updates for my repository and upstream?
- Oh no, I've lost my mind. I can't do it.
- ![image](https://gyazo.com/1102064e16a17999b6f8209610718784/thumb/1000)
    - Using GitHub Action as a free serverless execution environment, I've done it with Omoikane Embed and others, and it's useful, but Git wasn't designed for that purpose.
    - Upstream OSS is naturally updated.
    - Let's rename this repository and start anew.
        - Uh, maybe not.
            - GitHub's restriction that multiple forks cannot be done from the same repository.
            - Can I do it if I archive it? →I can't do it.
            - I guess I'll have to turn it off.
            - <img src='https://scrapbox.io/api/pages/villagepump/gpt/icon' alt='/villagepump/gpt.icon' height="19.5"/>You need to contact GitHub support and ask them to break the fork relationship for nishio/A2023.
                - reluctantly<img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>
            - clone and then DELETE what you have RENAMED
- exclamation of relief or disappointment
- Once again fork [https://github.com/nishio/quartz](https://github.com/nishio/quartz)
    - I want to avoid putting content here in the future.
    - I would like to say that this is a component and not a content holder.
    - `% git submodule add git@github.com:nishio/quartz.git quartz`
- `% git clone --depth 1 git@github.com:nishio/etude-github-actions.git`
    - I thought it would be faster if I just took the latest, but it's so slow.
- I'm getting tired, so I'm going to take a bath first.
- For now, let's run it once before automating.
    - `etude-github-actions/nishio/data.json` is the Japanese version.
    - The current English JSON is not in the repository for some reason, but `etude-github-actions/nishio/data_en_prev.json` is the English JSON for now?
    - It says `tasks/json_to_markdown/run.sh` in `tmp_0.sh`.
        - ScrapboxToObsidian] in a Git Submodule in `tasks/json_to_markdown`.
        - You did some minor experimental work on this last time.
tmp_1.sh

```
cp etude-github-actions/nishio/data_en_prev.json nishio.json
tasks/json_to_markdown/run.sh
```

    - quartzPages was created.
        - See this from quartz
        - `$ npx quartz create`
:

```
Choose how to initialize the content in `/Users/nishio/from_scrapbox/quartz/content`
│  ● Empty Quartz
│  ○ Copy an existing folder
│  ○ Symlink an existing folder
```

        - So we can just symlink it here.

:

```
  2 | title: '"I can\'t shake it" and "I won\'t shake  ...
 ---------------------^
     at Object.yaml [as parse] (../plugins/transformers/frontmatter.ts:55:35)
```


fixed: [https://github.com/nishio/from_scrapbox/commit/5374c3dc25148f6c70a2ace62b4e5396f68146c9](https://github.com/nishio/from_scrapbox/commit/5374c3dc25148f6c70a2ace62b4e5396f68146c9)

:

```
Cleaned output directory `public` in 4ms
Found 20937 input files from `content` in 196ms
Parsed 20937 Markdown files in 6m
Filtered out 0 files in 4ms
Emitted 20949 files to `public` in 5m
Done processing 20937 files in 11m
Started a Quartz server listening at http://localhost:8080
hint: exit with ctrl+c
```


![image](https://gyazo.com/b992ca4584829022573d3af2cd92f756/thumb/1000)
- sound effect for shock (usu. the disappointing kind)
- Oh, is that the one where the line becomes an object when metadata is attached to the Scrapbpx export?

from  [[Static generation in Quartz from Markdown and serve in Github Pages]]
- >  Can we use the Github Wiki as a comment form?
- > Would you like to ask a question or point out an error in an article on Github Issues?
- I see
    - I was thinking of making it possible to send information "I want this page to be improved" when the quality of the English translation is not good enough, but I was thinking of using Issues.

:

```
Failed to process `content/Infinite sum compression using the inverse of a formal power series.md`: URI malformed
     at decodeURI (<anonymous>)
     at transformInternalLink (../util/path.ts:89:38)
     at transformLink (../util/path.ts:207:20)
     at ../plugins/transformers/links.ts:104:49
```

I don't know how to fix it without a little more detail.

Oh, no!
- Are there countless cases of base64-encoded URLs being corrupted in the translation process?

I was dismayed to think there would be countless of them, but surprisingly, I was able to get down to three.
- I could see it locally.

If you publish this on GitHub Pages, you can publish it.
- I'm thinking the quality of the translation is not so good.
    - But that's okay because it's still not good enough.
- If you try to automate the publishing process, the above error must be resolved automatically.
    - Fundamentally, links should be judged as links and then only the title portion should be translated.

[Setting up your GitHub repository](https://quartz.jzhao.xyz/setting-up-your-GitHub-repository)
- This is designed to push to GitHub when synced, so the contents will be placed in this repository
    - Code and content managed in one place
    - That's what happens when you offer something for people who don't know much about it, and in fact I did that with omoikane-embed and others.
    - but not good in the long run because updates to the code are masked by updates to the content.
- [Hosting](https://quartz.jzhao.xyz/hosting)
    - This is also a GitHub Action that builds when updated, with code and content in bulk management.

public/ is created when build is done.
- ![image](https://gyazo.com/f59f0cc8bc96cd087190a2720c10aca2/thumb/1000)
    - I think we had the same conversation last time.
    - I've already commented out Component.Explorer and Component.TableOfContents.
    - Component.Graph?
    - Component.Search may be
    - Result of stopping Component.Graph
        - 54.58GB
    - Result of stopping Component.Search
        - not much different
    - There is a huge script tag under BODY.
        - I feel like I can't do anything about this.
Quartz 4.0 has a huge script tag at the end of the static HTML, 2.5MB per page. 20,000 pages is about 50GB, which is a problem. I searched GitHub Issues to see if there is a solution to this problem.
- <img src='https://scrapbox.io/api/pages/villagepump/gpt/icon' alt='/villagepump/gpt.icon' height="19.5"/>A problem with the generated file size of Quartz 4.0 has been reported on GitHub as Issue `#1607`. In it, the following solutions are listed
    - Main Causes
        - This is due to the recent update that added support for Mermaid.js, which allows JavaScript to be embedded directly in HTML files.
    - solution
        - Disabling Mermaid: You can disable Mermaid.js by changing the following settings in quartz.config.ts.
    - There have been reports of build sizes returning to normal simply by disabling Mermaid, which is the easiest solution currently available.
- Seriously?<img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/villagepump/takker/icon' alt='/villagepump/takker.icon' height="19.5"/>
- 330.4 MB now on the WWW.<img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>
Deploy the public part of the build result in a separate repository.
- [https://nishio.github.io/quartz_deploy/](https://nishio.github.io/quartz_deploy/)
- I got it.
    - Why this is showing up in the backlinks to this is a mystery to me.
        - [https://nishio.github.io/quartz_deploy/](https://nishio.github.io/quartz_deploy/)
        - [https://nishio.github.io/quartz_deploy/Tower-of-Sin-Babel](https://nishio.github.io/quartz_deploy/Tower-of-Sin-Babel)
    - [[History API]]がバグってるみたい<img src='https://scrapbox.io/api/pages/villagepump/takker/icon' alt='/villagepump/takker.icon' height="19.5"/>
        - From [quartz_deploy](https://nishio.github.io/quartz_deploy/) to [Tower-of-Sin-Babel [https://nishio.github.io/quartz_deploy/Tower-of-Sin-](https://nishio.github.io/quartz_deploy/Tower-of-Sin-) After moving from [quartz_deploy](https://nishio.github.io/quartz_deploy/) to [Tower-of-Sin-Babel](https://nishio.github.io/quartz_deploy/), pressing the browser's back button returns the URL field to [quartz_deploy](https://nishio.github.io/quartz_deploy/), but the content remains the same.
        - I thought something was wrong, but that's what I thought.<img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>
- It's kind of subtle...


---
This page is auto-translated from [/nishio/機械翻訳したScrapboxをQuartzで公開2024-11-24](https://scrapbox.io/nishio/機械翻訳したScrapboxをQuartzで公開2024-11-24) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.