---
title: "Natural Language Processing on Heroku"
---

Notes on the process of turning a locally experimented natural language processing algorithm into an API server on Heroku
(No consideration of whether it is appropriate to do this on Heroku → [[API server placement considerations]])

- I'll refer to my notes [[Heroku+Flask]] when I did something similar before.
    - Create a new working directory
        - I've thought about using existing repositories, but it's so complicated that it would take a long time to find the cause of a problem and be barren, so I'll try to keep it as simple as possible.
        - `$ mkdir regroup-split-server`
        - `$ cd regroup-split-server `
    - Create a virtual environment and work on VSCode
        - `$ python3 -m venv venv`
        - `$ code .`
        - View -> Terminal
        - `$ source venv/bin/activate`
    - Create a minimal server with Flask
        - `$ mkdir server`
        - `$ code server/__init__.py`
python

```
from flask import Flask

app = Flask(__name__)

def create_app():
    return app

@app.route('/')
def root():
    return "OK"
```

        - `$ pip install --upgrade pip`
        - `$ pip install flask`
        - Set environment variables in a file
            - `$ code .env`
.env

```
FLASK_APP=server
FLASK_ENV=development
```

            - `$ pip install python-dotenv`
        - `$ flask run`
            - Verify that it runs without problems and that you get an OK when you open [http://127.0.0.1:5000/](http://127.0.0.1:5000/)
        - `$ git init`
        - `$ code .gitignore`
.gitignore

```
venv/     
*.pyc
__pycache__/
```

            - `$ git commit -m 'minimal Flask server'`
                - Actually, I'm doing Cmd+Enter in the Source Control tab of VSCode.
    - Add [[gunicorn]] and deploy.
        - This also serves as [[HTTPS for Flask]], which is included in the minimum configuration because I think it is not possible to have only HTTP as a modern API server.
        - `$ pip install gunicorn`
        - `$ pip freeze > requirements.txt`
        - `$ code Procfile`
Procfile

```
web: gunicorn server:"create_app()"
```

        - `$ heroku create regroup-split-server`
        - `$ git commit -m "add gunicorn"`
        - `$ git push --set-upstream heroku master`
            - Build logs appear. Make sure it's not an error.
        - `$ heroku open`
            - Open the deployed one in a browser, making sure OK is displayed.

- I haven't figured out yet what to do with this deployment repository and what to do with the local R&D repository to keep it clean.
    - I'm sure I'll want to separate them under certain circumstances, but until I have a clearer idea of how I want to separate them, I'm going to do it in unison.
        - I've had a hard link with separate repositories, but I don't think it's a good idea.
        - I guess I'd better use a git submodule or pip to connect them.
            - [Resolving Application Dependencies with Git Submodules | Heroku Dev Center](https://devcenter.heroku.com/articles/git-submodules)
                - [[PIP for myself]]

    - Keep folders separate for easy separation in the future.
        - `$ mkdir server/regroup_split`
    - Copy files that look necessary
deploy.sh

```
cp rich_tokenizer.py ../regroup-split-server/server/regroup_split/
cp regroup_split.py ../regroup-split-server/server/regroup_split/
cp TAIL_TOKENS_TO_REMOVE.txt ../regroup-split-server/server/regroup_split/
cp HEAD_TOKENS_TO_REMOVE.txt ../regroup-split-server/server/regroup_split/
cp test/simplelines1.txt ../regroup-split-server/server/regroup_split/test
cp test/regression_test.json ../regroup-split-server/server/regroup_split/test
```


    - Run unit tests and check for errors.
        - `ModuleNotFoundError: No module named 'MeCab'`
            - $ pip install mecab
                - Don't do this see [[mecab on heroku]].
            - `$ pip install mecab-python3==0.996.5`

    - If the unit test passes, call the test from server/__init__.py
        - flask run to see if the test works on the local development server
        - It's easier to read error messages on the local development server than after deployment.
        - Common Corrections
            - Relative import `from .foo import bar`.
                - I usually run it as a script and experiment with it, but it is imported from the server and run as a module, so the import behavior changes.
                - Maybe it's better to [[IPython with %run -m]] on a regular basis.
            - path of a data file
                - If you're writing in a way that depends on the current directory at runtime, you'll get into trouble here.
                    - Use `DIR = os.path.dirname(__file__)`.

- Push to heroku when it works locally
    - `$ pip freeze > requirements.txt`
        - Don't forget to ADD and COMMIT!
        - I guess I should have done that when I INSTALLED it.
    - `$ git push`
        - Build errors [[mecab on heroku]].
    - After successful build, heroku open with 500 error
        - View runtime logs
            - `$ heroku logs --tail`
        - `TypeError: 'dict_keys' object is not reversible`
            - Python on heroku is 3.6 by default
            - > By default, newly created Python apps use the python-3.6.12 runtime. --- [Heroku Python Support | Heroku Dev Center](https://devcenter.heroku.com/articles/python-support)
        - Align the executed version with the one at hand
            - `$ echo python-3.8.7 > runtime.txt`
    - Test cases now work on heroku as well.

- Add an interface to return processed values passed from the server to the experimental scripts that have been running on the terminal and observing the results on the standard output.
    - In this case, it takes a string and returns a list of token strings.
    - At this point, it is up to you to decide whether you want to return a rich object or one that can be serialized in json.
        - By itself, it depends on the application.
        - I think the process of making json serializable is something that is required everywhere, so I think it would be good to have it on the library side.
        - Proper serialization can change as internal structures change, and
python

```
def process_single_line(line):
    tokens = tokenize(line)
    calc_split_priority(tokens)
    return dict(
        tokens=concat_tokens(tokens, " "),
        split=[concat_tokens(ts) for ts in split(tokens)])
```

- GET
python

```
@app.route('/api/', methods=['GET'])
def api():
    text = request.args["q"]
    ret = regroup_split.process_single_line(text)
    return ret
```

    - /api/?q=... Pass to GET to check operation with
    - Automatically serialized in JSON
- POST
python

```
@app.route('/api/', methods=['GET', 'POST'])
def api():
    if request.method == "GET":
        text = request.args["q"]
    else:
        text = request.json["q"]
    ret = regroup_split.process_single_line(text)
    return ret
```

    - `$ curl -X POST -H "Content-Type: application/json" -d '{"q":"test"}' localhost:5000/api/`
    - operation check
    - git push to make sure it works on heroku as well

- Create a client side that calls this API
python

```
import requests
import json

API_URL = "https://regroup-split-server.herokuapp.com/api/"
sample_text = "Ah, so people who are not used to the process of making lots of stickies and doing the KJ method don't have a good idea of how granular the information should be at the point of making the stickies in the first place. That's where the software needs to help."
payload = {"q": sample_text}
r = requests.post(API_URL, json=payload)
assert r.ok
for s in r.json()["split"]:
    print(s)

"""
Expected output:
Make lots of sticky notes.
People unfamiliar with the process of doing the KJ method.
How granular is the information at the point where you make a sticky note?
I can't pinpoint a good one.
Software needs to support
"""
```


- Call from JS
    - [[Flask-CORS]]
    - Done [[✅ longest line is ticked with one click]].

---
- [[Flask to HTTPS]]

---
This page is auto-translated from [/nishio/Herokuで自然言語処理](https://scrapbox.io/nishio/Herokuで自然言語処理) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.