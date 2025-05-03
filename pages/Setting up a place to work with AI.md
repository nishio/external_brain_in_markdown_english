---
title: "Setting up a place to work with AI"
---

I've mainly had a career of "writing and experimenting with code by myself," so I haven't had much experience with the problem of large diffs caused by differences in formatter values when each person develops in a multi-person project.
- I think I put in a de-facto formatter and fotmatOnSave when I introduced VSCode many years ago, that's about it.
- When I participated in multi-person projects, someone other than myself was often setting up the project.
- But when I started using [[Devin]], it became necessary to do formatter unification even if I was the only human being.

<img src='https://scrapbox.io/api/pages/nishio-en/o3/icon' alt='o3.icon' height="19.5"/>
- Decide to use "the same version for everyone", whether it is Black (de facto), Ruff format (fast + lint integrated), etc.
- Place settings in pyproject.toml directly under the project and minimize IDE-dependent settings.
- First, batch format all files once and commit
    - If you cut a single format-only commit, only logic changes will appear in diffs in subsequent PRs.
- Aligning the development environment
    - Put .vscode/settings.json in the repository and share it (works great if you have many VSCode users).
    - If you have other editors, you should also put .editorconfig so that line endings and indentations are aligned.

I didn't know about Black or Ruff. I guess I'm not autopep8 anymore or something.<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
Ruff is being used in a broadband AI, so I'm hoping it's the same.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>How do I know what my VSCode is now?
<img src='https://scrapbox.io/api/pages/nishio-en/o3/icon' alt='o3.icon' height="19.5"/>⌘/Ctrl + Shift + P → Format Document With... Execute
The extension name displayed as "default" in the popup is the tool used for save-time formatting

It was Black!<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>

`$ ruff format .`
I don't know if this is the right thing to do.

[https://chatgpt.com/c/68145ac2-8a58-8011-9937-43789ecdc38b](https://chatgpt.com/c/68145ac2-8a58-8011-9937-43789ecdc38b)


---
This page is auto-translated from [/nishio/AIとの協働の場を整える](https://scrapbox.io/nishio/AIとの協働の場を整える) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.