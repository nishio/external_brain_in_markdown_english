---
title: "Make # a comment in zsh"
---

<img src='https://scrapbox.io/api/pages/nishio-en/o3-mini-high/icon' alt='o3-mini-high.icon' height="19.5"/>In zsh, as in bash, "#" is used as a comment line. However, when typing directly in an interactive shell, lines beginning with # may be interpreted as commands unless setopt interactive_comments is enabled.

If you want the interactive shell to recognize a comment line as a comment when you type it, add `setopt interactive_comments` to your .zshrc and it will work just like bash.

[[zsh]]

---
This page is auto-translated from [/nishio/zshで#をコメントにする](https://scrapbox.io/nishio/zshで#をコメントにする) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.