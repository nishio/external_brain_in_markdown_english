---
title: "YouTube comment/transcript/live chat acquisition"
---

I put the code here: [https://github.com/nishio/from_youtube](https://github.com/nishio/from_youtube)
- Comments in real-time on YouTube Live are properly called "live chat", not "comments".
- No API key was needed to get live chat.
- I'm able to get comments/transcript/live chat as of 2024-11-15, but it's possible that an update on YouTube's side may stop it from working.

---

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I want to download YouTube comments in Python.

<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>The most common way to download YouTube comments in Python is to use the YouTube Data API v3 with libraries such as google-auth, google-auth-oauthlib, and google-auth-httplib2. The following is an overview of the procedure.

Get API Key
- Create a new project in the Google Cloud Console, activate YouTube Data API v3, and then obtain an API key.
    - I looked for it in the list but couldn't find it, I searched and found it.<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
    - ![image](https://gyazo.com/c7e1beefcfdddc725b20506736815042/thumb/1000)


Installing Python packages
- Install the package as follows
- $pip install google-auth google-auth-oauthlib google-auth-httplib2 google-api-python-client

Creating Codes
Use the obtained API key to retrieve comments from YouTube videos. Sample code is shown below.
...
- It worked, but what I wanted was "live chat", not "comments".

---
This page is auto-translated from [/nishio/YouTubeのコメント/トランスクリプト/ライブチャット取得](https://scrapbox.io/nishio/YouTubeのコメント/トランスクリプト/ライブチャット取得) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.