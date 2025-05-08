---
title: "OSS Weekly Reporter2025-05-07"
---

Oh, it looks like GitHub Actions are running successfully.
[https://github.com/nishio/oss_weekly_reporter/actions/runs/14874435303](https://github.com/nishio/oss_weekly_reporter/actions/runs/14874435303)

Nope, only Slack is done.
- Run non-Slack portions locally
    - The GitHub portion is OK.
    - > Could not get token from GitHub CLI: Command `'['gh', 'auth', 'token']'` returned non-zero exit status 1.
    - That's not good at all.
- `$ python -m src.call_openai_api slack --all-summary`
    - I see the channel name has changed and skip channel is off.
    - Fixed.



---
This page is auto-translated from [/nishio/OSS Weekly Reporter2025-05-07](https://scrapbox.io/nishio/OSS Weekly Reporter2025-05-07) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.