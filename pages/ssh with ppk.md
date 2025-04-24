---
title: "ssh with ppk"
---

- I was given a *.ppk file and told to use it to enter the server, but when I use ssh -i to specify it, it is in invalid format.
- Apparently pppk is a Putty format.
- Need to convert to openssh format [ref](https://superuser.com/questions/232362/how-to-convert-ppk-key-to-openssh-key-under-linux)
    - `puttygen INPUTFILE.ppk -O private-openssh -o OUTPUTFILE`
---
This page is auto-translated from [/nishio/ppkでssh](https://scrapbox.io/nishio/ppkでssh) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.