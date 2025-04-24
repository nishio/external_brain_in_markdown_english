---
title: "The story of how GPT4 suggested a way that could be done but ended up not being able to do it."
---

I asked [[GPT4]] for a different way to store cache files that I had stored in Git LFS.
I was wondering, "What is the best way to place or retrieve a cache file created by Github Actions? I want to access that file in my next action, but I don't need to keep a history of it."

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/> What is the best way to put and get cache file which created in Github Actions. I want to access the file in next time action, but no need to keep history.
<img src='https://scrapbox.io/api/pages/nishio-en/GPT/icon' alt='GPT.icon' height="19.5"/> GitHub Actions provide built-in support for caching dependencies and build outputs to improve workflow execution time. However, GitHub's cache is not meant to be a way to share data between jobs or workflows; it's meant to be used to speed up installing dependencies that you'd otherwise have to fetch from a remote server. As such, it's subject to a number of limitations and considerations:
- Cache storage is limited to 5 GB per repository.
- Not all types of files can be cached.
...
### However, if you're looking to share data between jobs or between different runs of the workflow, you might want to consider using GitHub's artifact support.

Artifacts allow you to persist data between jobs in a workflow, and they can be used to store data for use in a later job. They're also accessible after the workflow is completed, so they can be downloaded manually if needed.

Here is an example of how to use them:
...

You think you can do it, don't you?

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/> I want to store data on a run of a workflow, then on next day I want to use the stored data in the same workflow.
<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/> ### GitHub Actions does not directly provide a way to persist data between separate workflow runs.
 However, there are several ways you can achieve this:

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/> Can I share artifact files between different runs of the workflow?
<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/> As of my knowledge cutoff in September 2021, ### you cannot directly share artifact files between different runs
 of a GitHub Actions workflow. Artifacts are tied to the specific workflow run that created them, and they are not accessible across different workflow runs.

You can't do it!

---
This page is auto-translated from [/nishio/GPT4ができそうな方法を提案したけど結局できなかった話](https://scrapbox.io/nishio/GPT4ができそうな方法を提案したけど結局できなかった話) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.