---
title: "VSCode is blank with git rebase -i"
---


<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>when I use `git rebase -i`, VSCode generate empty page. How to fix it?
<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>When using git rebase -i, Git opens an editor for you to modify the list of commits. If you've configured Git to use VS Code as your editor and you're seeing an empty page, there may be an issue with how Git and VS Code are configured to interact.
- Here are some steps to troubleshoot and fix the issue: ...
- `$ git config --global core.editor "code --wait"`
    - The --wait flag is important because it keeps the VS Code instance open until you're finished editing.

[[Ask GPT4 about technology]].

---
This page is auto-translated from [/nishio/VSCodeがgit rebase -iで空白になる](https://scrapbox.io/nishio/VSCodeがgit rebase -iで空白になる) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.