---
title: "Push to other repo with GitHub Actions"
---

<img src='https://scrapbox.io/api/pages/nishio-en/Sonnet3.7/icon' alt='Sonnet3.7.icon' height="19.5"/>
The 403 error when pushing from GitHub Actions to another repository is due to the default `GITHUB_TOKEN` not having push permission to the other repository.

Solution:
1. create a Personal Access Token (PAT) on GitHub
    - Settings → Developer settings → Personal access tokens → Generate new token (classic)
        - Not the repo settings, but the personal one.<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
            - ![image](https://gyazo.com/46e81de84b91fef5b2c467d1f97d1cf9/thumb/1000)![image](https://gyazo.com/528db934d891a1c8c2c5547688f4f322/thumb/1000)
        - Give at least `repo` scope
    - Copy generated tokens

Add a new secret in the repository Settings → Secrets → Actions
    - Name: `PAT`.
        - Value: Copied token

3. modify the workflow file
yaml

```yaml
 name: Run update script
 run: |
  bash tasks/update_markdown/run.sh
 env:
  SID: ${{ secrets.SID }}
 GITHUB_TOKEN: ${{ secrets.PAT }} # change here
```


This will allow GitHub Actions to be pushed to another repository.
---
This page is auto-translated from [/nishio/GitHub Actionsで他のrepoにpush](https://scrapbox.io/nishio/GitHub Actionsで他のrepoにpush) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.