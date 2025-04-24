---
title: "git update-index --skip-worktree"
---

If I edit my local .vscode/settings.json while [[.vscode/settings.json]] already exists and is in the co-development repo, I get a status of "[[uncommitted changes]] exist" and [[stash is required every time]] when I pull the file. Problem, what should I do?

<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>Use git update-index --skip-worktree
- Benefit: If you change your local configuration file, Git will no longer track those changes.
- Procedure: 1.
    - Execute the following command to disable tracking for a specific file: "/files/files/files.html".
    - `$ git update-index --skip-worktree .vscode/settings.json`
- This means that if you change your local configuration, Git will not detect it and will not be subject to commit.
- If you want to track changes again, you can deactivate it with the following command: "deactivate".
    - `$ git update-index --no-skip-worktree .vscode/settings.json`
- This way, you can maintain your local configuration and avoid conflicts with the repository.


I see...<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>

[[Use npm instead of Deno]].

---
This page is auto-translated from [/nishio/git update-index --skip-worktree](https://scrapbox.io/nishio/git update-index --skip-worktree) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.