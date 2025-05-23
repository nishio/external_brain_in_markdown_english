---
title: "Devin's use in improving Team Mirai policy"
---

- [[Team Mirai]] Using Devin in Policy Improvement
I'll summarize it in bullet points as it might make an interesting case study for a Note article later.
- There are 1400+ PRs for the policy
    - [https://github.com/team-mirai/policy](https://github.com/team-mirai/policy)
        - [[Idombata policy making]] Effect of allowing modules to be proposed even by those who cannot use GitHub directly.
- If we try to analyze all of these cases, we will hit the Rate Limit (5000 cases / hour) of the Github API.
- If you ask [[Devin]] to do it, he tries his best to work with a web browser.
- Wrote code to get hourly up-to-date data and convert to JSON using Github Actions.
    - [https://github.com/team-mirai/random/tree/main/pr_analysis](https://github.com/team-mirai/random/tree/main/pr_analysis)
    - Now you can get 1,000 PRs per hour.
- Data is placed here.
    - [https://github.com/team-mirai/policy-pr-data](https://github.com/team-mirai/policy-pr-data)
- By instructing Devin in Japanese, I was able to use this data to extract specific conditions from all PRs and create a CSV
    - Instruct from Slack and have the resulting CSV attached to Slack.
    - Results were obtained in two minutes.
    - This has created a system where non-engineers can direct "the type of analysis that requires some implementation" 24 hours a day and get results in a matter of minutes.

---
This page is auto-translated from [/nishio/チームみらい政策改善でのDevinの活用](https://scrapbox.io/nishio/チームみらい政策改善でのDevinの活用) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.