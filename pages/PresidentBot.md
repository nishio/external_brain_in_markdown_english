---
title: "PresidentBot"
---

- The explanation for using [https://apps.twitter.com/](https://apps.twitter.com/) is out of date
    - > As of July 2018, you must apply for a Twitter developer account and be approved before you may create new apps. Once approved, you will be able to create new apps from developer.twitter.com.
- pip tweepy doesn't work with 3.7
    - I've already fixed it in master.
        - `$ pip install git+https://github.com/tweepy/tweepy`
    - If you put it in first with pip, you need to uninstall
- It was mumbled on my account, not on the bot's account.
    - I created a Twitter application name and a Twitter account with the same name, but the latter has nothing to do with it.
    - Ignore the access token on the app's dashboard, and use the account you want to mumble to get an OAuth authentication and access token to use it.
        - Does this expires over time? I'll check later.

---
![image](https://gyazo.com/469461fa50b93b1ac5216e60b4e0ac94/thumb/1000)

---
![image](https://gyazo.com/8a68d0e52eafea6a5819aa838a099659/thumb/1000)

I'm thinking of making a president bot for the hackathon.
As input data
- Books written by him
- Cybozu-style and other articles in which he speaks
and others.

- It should be easy enough to chop it up to the right length and Tweet it.
- Run it in an appropriate place (like Heroku?) and run it in an appropriate place (Heroku?)
- Tweet quotes from books with a link to Amazon
- Tweet quotes from articles with article link
- Translate into English with Google Translate and tweet
- output and posts without likes and retweets are suppressed.
    - Collect data on how much of each output was responded to in the subsequent 24 hours

Quite advanced content
- If you talk to them and say "follow me", they will follow you and reply to you with keywords of what you say.
- But you'd have to go this far to make it technically interesting.

---
This page is auto-translated from [/nishio/社長ボット](https://scrapbox.io/nishio/社長ボット) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.