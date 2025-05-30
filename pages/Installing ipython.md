---
title: "Installing ipython"
---

2022-12-04
They kindly tell me to let it through because it's not passing.
:

```
% pip3 install ipython     
Defaulting to user installation because normal site-packages is not writeable
Collecting ipython
...
WARNING: The scripts ipython, ipython3 and ipython3.10 are installed in '/Users/nishio/Library/Python/3.9/bin' which is not on PATH.
```

[[Defaulting to user installation because normal site-packages is not writeable]]

By the way, if you try to put it in with sudo, he tells you not to do that because it will clash with the system's package manager, and ignores you, kindly.
:

```
% sudo pip3 uninstall ipython
Password:
...
WARNING: Skipping ipython as it is not installed.
WARNING: Running pip as the 'root' user can result in broken permissions and conflicting behaviour with the system package manager. It is recommended to use a virtual environment instead: https://pip.pypa.io/warnings/venv
```


So we passed it by honestly.
.zshrc

```
export PATH=$PATH:/Users/nishio/Library/Python/3.9/bin
```


---
This page is auto-translated from [/nishio/ipythonのインストール](https://scrapbox.io/nishio/ipythonのインストール) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.