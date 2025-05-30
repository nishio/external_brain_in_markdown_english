---
title: "Chatbots in Mattermost"
---

    - [[Mattermost]] was introduced in [2019 Unexplored Junior
- [[tokoroten]] wanted to connect [[Vein]], and it was decided that everyone should be Hackable anyway.
- So now that everyone can connect to each other, I made a [[chatbot]] too.

- Configure Incoming Webhook.
    - After setting it up, try throwing a request with [[curl]].
    - `$ curl -i -X POST -d 'payload={"text": "Japanese!"}' https://mattermost....`
    - If set up correctly, it would look something like this
        - ![image](https://gyazo.com/e90b122c87fd934b6155d1179ab77345/thumb/1000)
        - The profile image setting was not a file upload, but an image URL.

- Set Slash Command.
    - I may not use it for the chatbot itself, but I'll do this to take it step by step.
    - Do it on the server at hand to make it easier to see what's going on.
    - `$ python3 -m http.server`
        - I set up an HTTP server on local port 8000.
        - Do it in a place where there is nothing to be seen because the files in the directory will be exposed.
    - `$ ngrok http 8000`
        - Tunneling to local port 8000 with [ngrok
        - Access `http://***.ngrok.io/` in a browser and make sure you can see inside the directory
    - Slash command settings
        - Request URL: `http://***.ngrok.io/`
        - Request Method: GET
    - Now when I run the slash command, I see this request arrive at the server
        - GET /?channel_id=***&channel_name=z-botplayground&command=%2Fnisbot&response_url=***&team_domain=***&team_id=***&text=&token=***&user_id=***&user_name=nishio
    - `http.server` returns HTML for this request, ignoring parameters, listing the files in the directory
    - The HTML is displayed on Mattermost.
        - ![image](https://gyazo.com/eaf77ef21c4891ea4e481088d7c9a98a/thumb/1000)
    - It is now confirmed that the server at hand and Mattermost can communicate with each other.
    - If you set the request method to POST, Mattermost will display
        - Command by `trigger 'nisbot' returned 501 Unsupported method ('POST') status.
        - and an error message appears. Reason that `http.server` returns 501 for POST

- Configure Outgoing Webhook.
    - Stuck in a subtle pitfall:.
            - [[Outgoing Webhook is not activated in Mattermost with the same wake word as the slash command]]
        - Cannot use both `/nisbot` and `nisbot foo` at the same time
        - Change the side of the slash command as appropriate.
    - Prepare a server capable of handling POST method requests
        - For example, use Flask
            - [Welcome | Flask (A Python Microframework)](http://flask.pocoo.org/)
        - Here's how to receive the POST.
            - [HTTP Methods](http://flask.pocoo.org/docs/1.0/quickstart/#http-methods)
            - State "Receive POST instead of GET.
            - If you make a mistake, ngrok will display "405 METHOD NOT ALLOWED
        - How to reply to Mattermost is in 10 of these.
            - [Outgoing Webhooks — Mattermost 5.11 documentation](https://docs.mattermost.com/developer/webhooks-outgoing.html)
        - In summary, the code looks like this
python

```
from flask import Flask
import json
app = Flask(__name__)

@app.route("/", methods=["POST"])
def hello():
    return json.dumps(dict(text="hello"))
```

        - `$ FLASK_APP=server.py flask run --port 8000`
            - Server started.
            - The only reason I'm specifying port 8000 is to avoid starting ngrok again by aligning it with http.server.
        - Now when I talk to him, he responds with hello.
            - ![image](https://gyazo.com/eb4d211c9ee896d8505666b6b7d02562/thumb/1000)

    - I want to handle parameters anyway because it's no fun to reply with a fixed string every time.
        - What name the parameter is passed by is written in 8 of this.
            - [Outgoing Webhooks — Mattermost 5.11 documentation](https://docs.mattermost.com/developer/webhooks-outgoing.html)
python

```
from flask import Flask, request
import json
app = Flask(__name__)

@app.route("/", methods=["POST"])
def hello():
    username = request.form["user_name"]
    text = request.form["text"]
    reply = f"{username} typed "{text}""
    return json.dumps(dict(text=reply))
```

        - ![image](https://gyazo.com/3f673f2cac3dc5767099cd698a3d35c7/thumb/1000)
        - Failure notes on the creation process
            - I forgot the request in `from flask import Flask, request` and got a 500 Internal Server Error.
            - 400 Bad Request is generated when "username" is used instead of "user_name".
            - 400 even if the content type is changed from the default urlencoded to json.
                - ![image](https://gyazo.com/b77eb98b3c5771f95a8ee21a95ae25e2/thumb/1000)

This time, I worked up to the point of creating a bot on the server at hand.
Personally, I'd like to try AWS Lambda next.
- [I made a Mattermost "praise bot" with Lambda and Python - Qiita](https://qiita.com/t15/items/5cae2fc9916363858f6c)
Also, in order to start without a trigger word
- [OAuth 2.0 Applications — Mattermost 5.11 documentation](https://docs.mattermost.com/developer/oauth-2-0-applications.html)
- I wonder? (I haven't read it thoroughly yet)
- Someone is building a BOT that receives all messages in Slack.
    - [I made a serverless BOT that auto-replies in Slack - Qiita](https://qiita.com/saitotak/items/822bf2dce7e3baa25ae0)

- Hitting Incoming WebHook from Python and making the chatbot talk.
    - `requests.post(url, json=dict(text="rebooting server..."))`
- I got carried away and messily implemented FORTH and connected it.
![image](https://gyazo.com/972ff7262e28caf82ab5d2dc371095a1/thumb/1000)


---
This page is auto-translated from [/nishio/Mattermostでチャットボット](https://scrapbox.io/nishio/Mattermostでチャットボット) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.