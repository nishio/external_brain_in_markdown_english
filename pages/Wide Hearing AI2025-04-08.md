---
title: "Wide Hearing AI2025-04-08"
---

from  [[Diary 2025-04-08]]
Wide Hearing AI2025-04-08
- [[public information AI]]
[https://github.com/digitaldemocracy2030/kouchou-ai/pull/228](https://github.com/digitaldemocracy2030/kouchou-ai/pull/228)

I'm willing to do this, but if this gets CLOSED, the discussion that's going on here will drift away.
- It might be useful to extract the "design decisions and reasons for them" from the discussions that took place in the issue and PR and document them.

git stash
git fetch
![image](https://gyazo.com/1b0eee3b2a4006c8c88df68b8b8d5db1/thumb/1000)
Gee wow!

![image](https://gyazo.com/556d1d9ef4ce18b752cfa8d73b573da4/thumb/1000)
This one.

`% git checkout cybozu-azure-settings       `
`% git rebase feature/azure-storage `
Successfully rebased and updated refs/heads/cybozu-azure-settings.

What should the [[Azure Blob Storage]] account name and container name look like?
<img src='https://scrapbox.io/api/pages/nishio-en/Devin/icon' alt='Devin.icon' height="19.5"/>
This section describes the naming conventions for Azure Blob Storage account names and container names:

Storage Account Name
Only lowercase letters and numbers are allowed
3 to 24 characters long
Must be unique worldwide
Examples: kouchouaistorage, companyname2023storage

Container Name
Only lowercase letters, numbers, and hyphens are allowed
3 to 63 characters long
Hyphens cannot be used consecutively
Examples: reports-container, kouchou-data
You may want to choose a name that is relevant to your project. For example:

Storage account: kouchouaistorage
Container: reports-data

---
There is a test result of 24eb
Make sure this goes away first.

Then create a new report
Then, as a more realistic test, update the repo, build and push, and make sure it doesn't disappear.

OK
Persistence with [[Azure Blob Service]] now works.
- Existing report has disappeared and will be reloaded.

`% git checkout main`
Switched to branch 'main'
Your branch is behind 'origin/main' by 83 commits, and can be fast-forwarded.
    - (use "git pull" to update your local branch)

[https://github.com/digitaldemocracy2030/kouchou-ai/pull/261](https://github.com/digitaldemocracy2030/kouchou-ai/pull/261)
done


---
This page is auto-translated from [/nishio/広聴AI2025-04-08](https://scrapbox.io/nishio/広聴AI2025-04-08) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.