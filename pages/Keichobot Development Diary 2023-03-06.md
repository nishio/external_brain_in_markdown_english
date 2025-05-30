---
title: "Keichobot Development Diary 2023-03-06"
---

[[Heroku]]
- Install [[Heroku CLI]]
    - [https://devcenter.heroku.com/articles/heroku-cli#install-the-heroku-cli](https://devcenter.heroku.com/articles/heroku-cli#install-the-heroku-cli)
- Run your app locally
    - [https://devcenter.heroku.com/articles/heroku-local](https://devcenter.heroku.com/articles/heroku-local)
- There is no gunicorn.
    - Why would that be the case if there is a venv in the first place?
    - pip install -r requirements.txt
    - numpy, scikit-learn, scipy, mecab-python3, etc. are mocked up
    - Why?
- Will this go through deployment in the first place?
    - Oh, it went through.
    - Python 3.8 in Heroku.
- Local is 3.9, so there's some discrepancy.
    - [[mecab on heroku]] also looks shady

- `$ brew install python@3.8`
    - mecab-python3 is mocking up
        - I'll put it in brew, which lacks mecab and swig to begin with.
- `$ brew install llvm`
- Motion!

conversation log
    - [[Keichobot+GPT test 2023-03-06]]
    - [[LLM, regression testing and A/B testing]]

next action
- I want a summary command.
- Turn prompts to take advantage of original output

- [[Keichobot Development Diary 2023-03-07]]

- [[Keichobot Development Diary]]
[[Keichobot]]

---
This page is auto-translated from [/nishio/Keichobot開発日記2023-03-06](https://scrapbox.io/nishio/Keichobot開発日記2023-03-06) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.