---
title: "Report generation from Slack and GitHub"
---

Slack
- [https://x.com/nishio/status/1904480017335431447](https://x.com/nishio/status/1904480017335431447)
    - Slack commentary on Digital Democracy 2030 (2025-03-25) generated
- I also generated commentary on the past three days, which has been more specific.
    - [https://gist.github.com/nishio/0a8ba0c3a1d7f7b6742966cafc0cf547](https://gist.github.com/nishio/0a8ba0c3a1d7f7b6742966cafc0cf547)
- I would like to ask that anyone who has something to share with the group, please share it with us here.
    - [https://docs.google.com/document/d/1plggszRTxEEYUcZuCLiHkPrBsMtxr3RQpctKtZe5y4M/edit?tab=t.0](https://docs.google.com/document/d/1plggszRTxEEYUcZuCLiHkPrBsMtxr3RQpctKtZe5y4M/edit?tab=t.0)
    - Made only from Slack, a broadband AI.

GitHub
- > The following is a brief summary of the main events that occurred in the "digitaldemocracy2030/kouchou-ai" repository during the week of 2025-03-20 to 2025-03-27. There are many new features and bug fixes, and the project has evolved a lot.
- [https://gist.github.com/nishio/82918f0652a420352ccf84d67ce95562](https://gist.github.com/nishio/82918f0652a420352ccf84d67ce95562)


GitHub Action.
uses: nishio/gsheet-slack-logger@main
is processed based on the definitions in action.yml in the nishio/gsheet-slack-logger@main repository

action.yml

```yaml
runs:
  using: 'docker'
  image: 'Dockerfile'
```


`$ docker build -t gsheet-slack-logger .`
`$ docker run --rm --env-file .env gsheet-slack-logger`


---
This page is auto-translated from [/nishio/SlackとGitHubからのレポート生成](https://scrapbox.io/nishio/SlackとGitHubからのレポート生成) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.