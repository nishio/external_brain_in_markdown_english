---
title: "IPython with %run -m"
---

I was doing `%run foo.py -t` in IPython, but it would be more convenient to `%run -m foo -t` when I'm in the phase of using it as a component from other projects.
- The former does not allow relative imports.
    - > What you probably did is you tried to run moduleX or the like from the command line. When you did this, its name was set to __main__, which means that relative imports within it will fail, because its name does not reveal that it is in a package.
        - [python - Relative imports for the billionth time - Stack Overflow](https://stackoverflow.com/questions/14132789/relative-imports-for-the-billionth-time/14132912#14132912)
- The latter is executed as a module as when imported
    - In other words, you can import relative


I also `-m`venv and unittest.


Ahh. In this style, the global scope of the executed script is separate from the scope on the ipython side?
- I can't just leave a function in place and call it as needed.
- Do you call them by args properly?
    - This is not possible when you want to observe the internal state in the first place.
- If you just want to change the entry point of a command, why not separate the scripts themselves in the first place?

[[-m pytest]]

---
This page is auto-translated from [/nishio/IPythonで%run -m](https://scrapbox.io/nishio/IPythonで%run -m) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.