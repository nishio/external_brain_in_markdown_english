---
title: "BOT exit messages and their side effects"
---

In heroku, the server will shut down in 30 minutes if there is no access.
So I added a function to bots deployed on heroku that sends "sleeping..." when it finishes. at the end of the deployment.
python

```
import atexit
@atexit.register
def exit():
    requests.post("<URL>", json=dict(text="(heroku)sleeping..."))
```


But this message is sent to heroku, and as soon as I go to sleep, it wakes me up.
![image](https://gyazo.com/aa0923655535fd9834c40ee92c14edbe/thumb/1000)

I was wasting my free slots by repeatedly going to sleep and waking up every 30 minutes throughout the night, so I decided to quit.


---
This page is auto-translated from [/nishio/ボットの終了時メッセージとその副作用](https://scrapbox.io/nishio/ボットの終了時メッセージとその副作用) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.