---
title: "Git LFS"
---

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>What do you do when you want to use GitLFS because the file is too big in Github?
<img src='https://scrapbox.io/api/pages/nishio-en/GPT-4/icon' alt='GPT-4.icon' height="19.5"/>
- To use Git LFS, follow these steps
    - Install Git LFS: Download and install from the official website ( [https://git-lfs.github.com/](https://git-lfs.github.com/) ).
    - In a terminal, type git lfs install and run it.
    - Specify a large file extension: git lfs track "*. extension" (e.g. git lfs track "*.psd") and run it.
    - A .gitattributes file will be generated, which should be included in the commit.
    - Execute git add, git commit, and git push as usual.
- Now large files will be managed using Git LFS.
---
This page is auto-translated from [/nishio/Git LFS](https://scrapbox.io/nishio/Git LFS) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.