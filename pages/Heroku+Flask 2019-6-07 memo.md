---
title: "Heroku+Flask 2019-6-07 memo"
---

from [[Heroku+Flask]]
Heroku+Flask 2019-6-07 memo
`$ heroku buildpacks:set heroku/python`
Add the necessary files and git push heroku master
- new file:   Procfile
- new file:   requirements.txt
- new file:   runtime.txt
I'm getting "App not compatible with buildpack" even though I'm doing
- I thought I did, but I just did a git add and didn't commit.


- I wrote something like `web:FLASK_APP=server.py flask run --port 8000` in the procfile, but it gets killed as soon as flask is started
log

```
019-06-06T16:06:39.226032+00:00 heroku[web.1]: Starting process with command `FLASK_APP=server.py flask run --port 3000`
2019-06-06T16:06:41.580063+00:00 app[web.1]:  * Serving Flask app "server.py"
2019-06-06T16:06:41.580088+00:00 app[web.1]:  * Environment: production
2019-06-06T16:06:41.580091+00:00 app[web.1]:    WARNING: This is a development server. Do not use it in a production deployment.
2019-06-06T16:06:41.580137+00:00 app[web.1]:    Use a production WSGI server instead.
2019-06-06T16:06:41.580145+00:00 app[web.1]:  * Debug mode: off
2019-06-06T16:06:43.000795+00:00 app[web.1]:  * Running on http://127.0.0.1:3000/ (Press CTRL+C to quit)
2019-06-06T16:07:17.795885+00:00 heroku[router]: at=error code=H20 desc="App boot timeout" method=POST path="/" host=yagokoro.herokuapp.com request_id=3c62ce00-bbe8-4ac9-8ad7-b608b884c188 fwd="163.43.120.164" dyno= connect= service= status=503 bytes= protocol=https
2019-06-06T16:07:39.290453+00:00 heroku[web.1]: Error R10 (Boot timeout) -> Web process failed to bind to $PORT within 60 seconds of launch
2019-06-06T16:07:39.290453+00:00 heroku[web.1]: Stopping process with SIGKILL
2019-06-06T16:07:39.394293+00:00 heroku[web.1]: State changed from starting to crashed
2019-06-06T16:07:39.376614+00:00 heroku[web.1]: Process exited with status 137
```


I decided to pinch gunicorn based on other articles.
- Not sure why this is necessary.
- Reference: [Re: Heroku life starting from zero with Flask - environment building and hello world - Qiita](https://qiita.com/ymgn_ll/items/96cac1dcf388bc7a8e4e)

I thought I should have used 5119 for Outgoing Webhook because the log shows the following, but I'm glad I used 80.
- > Listening at: [http://0.0.0.0:5119](http://0.0.0.0:5119)

At any rate, now I have a fixed URL that connects regardless of the state of my machine.


---
This page is auto-translated from [/nishio/Heroku+Flask 2019-6-07 memo](https://scrapbox.io/nishio/Heroku+Flask 2019-6-07 memo) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.