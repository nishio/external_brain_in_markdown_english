---
title: "Deploy to Heroku"
---

- Create an account on [Heroku
- Follow the instructions to install the CLI
- Create App
- `$ heroku login`
- `$ heroku create`

- `$ heroku git:remote -a <app name>.`
- `$ git add .`
- `$ git commit -am "make it better"`
- `$ git push heroku master`
    - A lot happens on the other side.

- `$ heroku run python tweet.py`
    - operation check

- Scheduler Registration
    - You have to register your credit card before
        - Verify now at [https://heroku.com/verify](https://heroku.com/verify)
    - `$ heroku addons:create scheduler:standard`
    - `$ heroku addons:open scheduler`
    - browser will start up
    - You don't have a lot of spacing options.
        - ![image](https://gyazo.com/69fe020405cc736c2a2ed8362caebd0d/thumb/1000)
- View Error Log
    - heroku logs --tail --app <app-name>

---
This page is auto-translated from [/nishio/Herokuにデプロイ](https://scrapbox.io/nishio/Herokuにデプロイ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.