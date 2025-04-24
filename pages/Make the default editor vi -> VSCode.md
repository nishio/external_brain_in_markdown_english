---
title: "Make the default editor vi -> VSCode"
---

from  [[Mac Diary 2022]]
The default editor was vi.
[[VSCode]].

There's no CODE in PATH to begin with, what are we going to do 2022/11/26?
[macos - How to open Visual Studio Code from the command line on OSX? - Stack Overflow](https://stackoverflow.com/questions/29971053/how-to-open-visual-studio-code-from-the-command-line-on-osx)
> After installation, launch VS Code. Now open the Command Palette (F1 or ⇧+⌘+P on Mac) and type shell command to find the Shell Command: Install 'code' command in PATH command.

[[.bashrc]]
.bashrc

```
export EDITOR=code
```



---
This page is auto-translated from [/nishio/デフォルトエディタがvi→VSCodeにする](https://scrapbox.io/nishio/デフォルトエディタがvi→VSCodeにする) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.