---
title: "Read/write Windows shared folders in Ubuntu"
---

`$ mount -t cifs -o username=***,password=***,uid=$(id -u),gid=$(id -g) //*1*/Users/nishio/Documents/shared ~/shared`
- *1*: IP address of the Windows machine
- Share files in advance.

If you just read it, you don't need `uid=$(id -u),gid=$(id -g)`, but the owner of the directory is root, so you get an error when you try to create a file.

Read/write [[shared folder]] in [[Windows]] in [Ubuntu
[[cifs]]: [[Samba]]
- [[permission]]

---
This page is auto-translated from [/nishio/Windowsの共有フォルダをUbuntuで読み書き](https://scrapbox.io/nishio/Windowsの共有フォルダをUbuntuで読み書き) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.