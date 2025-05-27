---
title: "Multiple DevinOrgs cannot be connected to a single GitHubOrg."
---

![image](https://gyazo.com/3a14f1bd52fde78842437d2b570146da/thumb/1000)
<img src='https://scrapbox.io/api/pages/nishio-en/o3/icon' alt='o3.icon' height="19.5"/>
- Devin's GitHub integration is installed as a GitHub App in a GitHub Organization, and the installation ID is tied to a single Devin Organization (tenant).
- For this reason, it is not possible to have "multiple Devin Organizations" connected to the same GitHub Organization at the same time.
- If there is already a Devin Organization connected, it is necessary to uninstall that linkage first and then reconnect another Devin Organization.
- On the other hand, within a single Devin Organization, any number of members and any number of sessions can be run concurrently, so there is no need to worry about normal team development.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
- Well, a form of development that has a permissionless volunteer organization outside the main organization is not "normal team development."
- policy
    - Create a new org like team-mirai-volunteers (tmv below because it's long)
    - Even if Devin created a PR on tmv, he can merge it into team-mirai
    - I think tmv should include a Github Action that pulls when team-mirai is updated.


---
This page is auto-translated from [/nishio/ひとつのGitHubOrgに複数のDevinOrgは接続できない](https://scrapbox.io/nishio/ひとつのGitHubOrgに複数のDevinOrgは接続できない) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.