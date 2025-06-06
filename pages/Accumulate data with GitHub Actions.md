---
title: "Accumulate data with GitHub Actions"
---

- Method 1: Commit to main
    - first thing one does in the morning
    - A large number of data update commits are plugged in during source code version control, so it is difficult to follow the commit log when you want to continue the implementation after a while.
- Method 2: Create a data branch and commit
    - It looks good at first glance, but the trap is that if you want to analyze the latest data with the latest code and do a git checkout data, the code will rewind to the point where the data branch was generated.
    - rebase the data branch into main's HEAD
        - git checkout data && git rebase main
        - But the history changes, so you'll have to git push -f
        - Alternatively, you can use git merge main
    - I did this configuration with [[OSS Weekly Reporter]] and had a lot of trouble getting it to stabilize.
        - While code modification is a cancer, you have to do the above work properly, without leaking when you want to do something with the latest implementation for the latest data.
        - The data branch is updated by GitHub Actions, so further recovery is needed if you accidentally forget to push it.
- Method 3: Create a dedicated repository for date
    - I'm thinking as of 2025-06-05 that this is a good idea.
        - Better to be loosely coupled.
            - Code can be made public but data can be made open, and vice versa.
    - To push to other repositories, you need to create a PAT (Personal Access Token) that has permission to do so after setting Organization.
        - GITHUB_TOKEN, which is automatically granted to GitHub Actions, only has permissions "limited to the repository containing the workflow".
        - Enable "Allow access via personal access tokens" in Organization Settings → Personal access tokens → Settings

- Method x: Place on release
    - I've done it before, but I feel like it's complicated.
    - Advantages of loose file size restrictions

- Method y: Upload to Gist
    - Can be used when you want to deliver "latest data" that is not large in size in the form of a GET API that can be fetched from the front end.


---
This page is auto-translated from [/nishio/GitHub Actionsでデータを溜め込む](https://scrapbox.io/nishio/GitHub Actionsでデータを溜め込む) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.