---
title: "Jupyter Notebook"
---

- breakpoint
    - You can use `import IPython; IPython.embed()` to do what you used to do with `import pdb; pdb.set_trace()`.
    - It can be used not only for Jupyter but also for running scripts on the console.
- Post-mortem
    - In normal scripts, -mpdb will enter interactive debugging with pdb when an exception occurs.
    - Similarly for ipython in the console by doing %pdb
    - In Jupyter Notebook, %debug to enter interactive debugging after an exception occurs
- profiling
    - %timeit %%timeit: timeit
    - %prun %%prun: cProfile
    - line_profiler memory_profiler
        - !pip install line_profiler memory_profiler
        - %load_ext line_profiler
        - %load_ext memory_profiler


---
This page is auto-translated from [/nishio/Jupyter Notebook](https://scrapbox.io/nishio/Jupyter Notebook) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.