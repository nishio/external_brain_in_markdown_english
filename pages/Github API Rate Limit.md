---
title: "Github API Rate Limit"
---

o3 research
<img src='https://scrapbox.io/api/pages/nishio-en/o3/icon' alt='o3.icon' height="19.5"/>
- When calling the GitHub API from GitHub Actions, the "range" and upper limit of the primary rate limit depends on which token you use to authenticate.
    - GITHUB_TOKEN (default): 1 000 requests/hour per repository. All workflows/jobs in the same repository share this bucket.
    - Personal Access Token / OAuth access token: 5 000 requests/hr per user (15 000 requests/hr if owned by Enterprise Cloud organization).

---
This page is auto-translated from [/nishio/Github API Rate Limit](https://scrapbox.io/nishio/Github API Rate Limit) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.