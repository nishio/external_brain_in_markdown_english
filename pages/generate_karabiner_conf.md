---
title: "generate_karabiner_conf"
---

- I didn't want to edit the Karabiner configuration file by hand, so I wrote a program to generate it.
    - 2018-08-20 Generate Orz array
    - I wanted to use [[shio shift]] with Karabiner alone, so I made it so that it can be used with different configuration files.

setup file
- SIMPLE_KEY_CHAINS.txt
SIMPLE_KEY_CHAINS.txt

```
a u wo vu
```

    - Original key, no shift, shift left, shift right
    - `? is blank`
- SPECIAL.txt
    - SIMPLE_KEY_CHAINS.txt is difficult to work with when symbols and shifts are involved, so there is a separate file for symbols.
SPECIAL.txt

```
1LEFT ^slash #Hateful
```

    - ^ is shift
- Ideally, it is easy to understand that the data is generated from [[keylayout]] data
    - I made it and will use it for a while.

- Repository [https://github.com/nishio/generate_karabiner_conf](https://github.com/nishio/generate_karabiner_conf)

---
This page is auto-translated from [/nishio/generate_karabiner_conf](https://scrapbox.io/nishio/generate_karabiner_conf) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.