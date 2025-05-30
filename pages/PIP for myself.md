---
title: "PIP for myself"
---

I'm not enthusiastic enough to register with PyPI, but I'll put the code pieces that I want to use in multiple projects on Github so that I can install them with pip.
Fixing the version and keeping it up-to-date can be done by the pip itself, so there is less to think about.

- Write setup.py
    - Minimal official commentary
    - [Minimal Structure — Python Packaging Tutorial](https://python-packaging.readthedocs.io/en/latest/minimal.html)
- First, make sure you can pip install on your local file system
    - `$ pip install .`
- Push to Github
- Make sure you can pip install from Github
    - `$ pip install git+https://github.com/nishio/rich_tokenizer`


- This seems to lose the information about the install from git when pip freeze is done.
    - `$ pip install git+https://github.com/nishio/rich_tokenizer`
- This looks good.
    - `$ pip install -e git+https://github.com/nishio/rich_tokenizer#egg=rich_tokenizer`
- This would output `-e git+[https://github.com/nishio/rich_tokenizer@4284....](https://github.com/nishio/rich_tokenizer@4284....) .af7e#egg=rich_tokenizer
- [python - How to state in requirements.txt a direct github source - Stack Overflow](https://stackoverflow.com/questions/16584552/how-to-state-in-requirements-txt-a-direct-github-source)

reference
- [python - pip install from git repo branch - Stack Overflow](https://stackoverflow.com/questions/20101834/pip-install-from-git-repo-branch)
    - [Enabling pip installation of commands created in Python via GitHub | Developers.IO](https://dev.classmethod.jp/articles/pip-install-via-github-command/)
    - [https://github.com/pallets/flask](https://github.com/pallets/flask) is a good sample
    - [navdeep-G/setup.py: 📦 A Human's Ultimate Guide to setup.py.](https://github.com/navdeep-G/setup.py)
    - [Minimal Structure — Python Packaging Tutorial](https://python-packaging.readthedocs.io/en/latest/minimal.html)
---
This page is auto-translated from [/nishio/自分用pip](https://scrapbox.io/nishio/自分用pip) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.