---
title: "Static generation in Quartz from Markdown and serve in Github Pages"
---

from [/villagepump/Markdown to generate static in Quartz and serve in Github Pages](https://scrapbox.io/villagepump/Markdown to generate static in Quartz and serve in Github Pages) 2023-11-30

<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>The following is a summary

### Generate a static site from Markdown and host it on GitHub Pages
.
Conversion and Generation
- Scrapbox JSON to Markdown ([[from_scrapbox]] ([https://github.com/nishio/from_scrapbox](https://github.com/nishio/from_scrapbox) ))
- Generate a static site using Quartz ([[Quartz]]( [https://quartz.jzhao.xyz/](https://quartz.jzhao.xyz/) ))
- Need to add frontmatter, and adjustment to Obsidian format is an issue.

Issues and Responses: 1.
- Correction of original data and Markdown structure.
- Wikilinks support and plugin adjustments.
- Eliminated shortcomings of Quartz's Explorer plugin (bloated page link issue).

Deploy: 1.
- Deploy using GitHub Pages.
- Solves the problems of file size limitation (1GB) and build time limitation.
- Reduce build time by removing unnecessary links.

Final success and static site hosting complete: [https://nishio.github.io/quartz/](https://nishio.github.io/quartz/)

--- raw

2023-11-30
margin for pasting together (e.g. two pieces of paper)<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
- Markdown is converted from Scrapbox JSON at [nishio/from_scrapbox#655cbb2caff09e0000e993e0
- I use [[Quartz]] for static generation.
    - [[Static delivery in Quartz]]

from [[nishio/from_scrapbox]]
- Generate Static Site from Markdown and serve in Github Pages
- <img src='https://scrapbox.io/api/pages/nishio-en/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>Obsidian Vault at Quartz] at
    - reading...
    - Is [[Hugo]] being used? Is the language Golang?
        - [https://gohugo.io/documentation/](https://gohugo.io/documentation/)
        - [https://quartz.jzhao.xyz/](https://quartz.jzhao.xyz/)
            - > Quartz requires at least Node v18.14 and npm v9.3.1 to function correctly.
                - Oh, that's Node.
    - Is a light conversion of the frontmatter grant needed to go from Obsidian format to Quartz format?
        - [https://quartz.jzhao.xyz/authoring-content](https://quartz.jzhao.xyz/authoring-content)
            - There are aliases, tags
            - I'm not sure if it's just the minimum TITLE.
            - Currently there is no title information in Markdown created by ScrapboxToObidian.
                - It's in the file name.
                - Are you okay? Is there any information lost?
                - `page["title"].replace(/\//gi, "-")`
                - Hmmm, if you don't want Obsidian format output, I think it's better to branch out [here](https://github.com/nishio/from_scrapbox/commit/0cb3ebf89bfe923099daba08e09e83cc10c7e1f1). if you don't want Obsidian format output.
    - [https://quartz.jzhao.xyz/features/wikilinks](https://quartz.jzhao.xyz/features/wikilinks)
        - So Obsidian supports Wikilinks and Quartz does as well.
- <img src='https://scrapbox.io/api/pages/nishio-en/shoya140/icon' alt='shoya140.icon' height="19.5"/>The [[well diary]] of the [[well diary]] was generated from Next.js
    - This one looks more flexible.
    - I don't know much about Quartz, but it would be nice to be able to customize it as easily as this.
- study
    - Can we use the Github Wiki as a comment form?
        - At least the Wiki has an option to allow anyone to write on it.
    - Do you want to ask a question or point out an error in an article on Github Issues?
- set in motion
    - Node was said to be out of date and re-installed.
    - ![image](https://gyazo.com/d70ad0a72627036c89a0031649517031/thumb/1000)
    - ![image](https://gyazo.com/2d059ae2da054bad7d2c61403717d6b9/thumb/1000)
    - hmm
    - ![image](https://gyazo.com/82353ebe17bb306ad10ca28430561a4e/thumb/1000)
    - This is garbage original data [[2020-01-16]].
    - [fixed](https://github.com/nishio/from_scrapbox/commit/462310104e18003121685272ea28c7f3a43980ca)
- ![image](https://gyazo.com/12627f7106e6ca3ef28f7b216c63df1f/thumb/1000)
    - No matter how I look at it, it's a stupid mistake, not enough space between div and style, but I don't know where to fix it.
    - ![image](https://gyazo.com/f2ab19599bbdf51a769ab94fed42e3ac/thumb/1000)
        - Ah, the original data.
- ![image](https://gyazo.com/9f30f00bbee59351ff3aab1c284d9d5b/thumb/1000)
    - It took me 20 minutes to get it to work, it looks like I've managed it, though I'm getting warnings.
    - ![image](https://gyazo.com/39ab4df38bad311978fbf02f2f64f29c/thumb/1000)
    - There's no index.md, so it's a 404.
- ![image](https://gyazo.com/656074928e4a7a3223c28faf892be76a/thumb/1000)
    - It looks like it's displayed properly, at least.
    - Both Explorer on the left and Backlink on the right seem to be in ABC order.
        - I wish I had a better order.
        - Well, that's an improvement, not a 0 to 1, so we'll get to that later.
Explore Deploy
- Ha, what a complication!
    - [Hosting](https://quartz.jzhao.xyz/hosting)
    - There's a tricky detail cover-up going on.
- I don't know what to do. This is a pain in the ass.
- I haven't walked at all today and I don't get enough exercise, so I'll think about it while I walk anyway.
- Sleepy, close to the limit of today's activity (maybe already past).
- I'm wondering if following the instructions won't work as described? I'm thinking, but I'll just do it the way it's described anyway.
- furthermore
bash

```
% git status
On branch v4
Your branch is up to date with 'origin/v4'.

Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        deleted:    content/.gitkeep
        modified:   package-lock.json

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        content

no changes added to commit (use "git add" and/or "git commit -a")
```

- procedure
    - > Head to “Settings” tab of your forked repository and in the sidebar, click “Pages”. Under “Source”, select “GitHub Actions”.
    - You said "forked" as a matter of fact.
    - `$ git remote rename origin upstream`
    - `$ git remote add origin https://github.com/nishio/quartz.git`
    - I don't know if this is the right thing to do.
- Configure Github Pages with forked quartz repositories.
    - ![image](https://gyazo.com/d0b529d43787e3bf540daea9b1b6517a/thumb/1000)
- Now we can deploy (we are doing it from the build again on Github Action).
- And that's not what I want to do!
    - Well, but if the repositories are separated, it's okay anyway.
- You can't Deploy!
    - >  System.IO.IOException: No space left on device : '/home/runner/runners/2.311.0/_diag/Worker_20231129-132926-utc.log'
    - What's so big about it?
    - ![image](https://gyazo.com/57f9426d7af9d04e2803d0780e652d15/thumb/1000)
    - What, you can't help it?
    - > Published GitHub Pages sites may be no larger than 1 GB. [About GitHub Pages - GitHub Docs](https://docs.github.com/en/pages/getting-started-with-github-pages/about-github-pages)
    - Cloudfrare Pages, you say?
        - > Builds will timeout after 20 minutes. [Limits · Cloudflare Pages docs](https://developers.cloudflare.com/pages/platform/limits/)
        - This one will probably catch on...
    - Even pages with almost no content have 2.4 MB per page.
        - `Component.DesktopOnly(Component.Explorer())`
        - Let's turn this off.
        - I turned it off and a build that used to take 20+ minutes now takes 2 minutes.
        - Conclusion, that the implementation of this plugin is not able to assume a user with 10,000 pages.
            - Embedding links to all pages on all pages, so the file size swells by the order of squares.
    - Done! [https://nishio.github.io/quartz/読者向けLinks](https://nishio.github.io/quartz/読者向けLinks)


---
This page is auto-translated from [/nishio/MarkdownからQuartzで静的生成してGithub Pagesでserveする](https://scrapbox.io/nishio/MarkdownからQuartzで静的生成してGithub Pagesでserveする) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.