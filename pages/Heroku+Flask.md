---
title: "Heroku+Flask"
---

2020-09-15: Work note for running an API server for machine learning, natural language processing, etc. on heroku.
- 2021-01-18:  [[Natural Language Processing on Heroku]]
- 2021-10-14: [[FastAPI]] is also an option and should be considered (this time I tried FastAPI for a bit and then went back to Flask).

First, create a minimal server and run it locally.
- `$ python3 -m venv venv`
- `$ source venv/bin/activate`
- create "server/__init__.py" and write minimal server
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

    - Minimal server implementation
    - I had a habit of doing app.run with `if __name__ == "__main__"`, but I don't do that anymore, even in official Flask tutorials.
        - Specify the module to be started in the environment variable, and start it with flask run.
            - [explanation on the heroku side](https://devcenter.heroku.com/articles/flask-memcache) does that too.
            - Setting environment variables may seem tedious, but you can use dotenv
            - The official explanation uses [[Flask Blueprint]], but I decided that's not necessary at the minimum.
        - create_app is used to call from gunicorn later
- `$ python server/__init__.py`
    - `ModuleNotFoundError: No module named 'flask'`
        - `$ pip install --upgrade pip`
        - `$ pip install flask`
    - OK
- `$ flask run`
    - NG because environment variables are not set
    - > Error: Could not locate a Flask application. You did not provide the "FLASK_APP" environment variable, and a "wsgi.py" or "app.py" module was not found in the current directory.
- create ".env" file
    - `$ code .env`
:

```
FLASK_APP=server
FLASK_ENV=development
```

- `$ pip install python-dotenv`
- `$ flask run`
    - OK
    - If I look at [http://127.0.0.1:5000/](http://127.0.0.1:5000/) in my browser it says OK

Deploy to heroku
- `$ git init`
- create ".gitignore"
:

```
venv/
.env

*.pyc
__pycache__/
```

    - .env ignore?
        - If you don't IGNORE, you don't need to do $ heroku config:set FLASK_APP=server later
        - This is to avoid the common accident of putting API keys, etc. that should not be made public in .env and pushing them to the public repository.
- `$ git add .`
- `$ git commit -m 'minimal Flask server'`

- `$ heroku create foo-server`
    - This is creating an app from a local console, but if you are already using it from a browser, just follow the instructions in the browser.
        - `$ heroku git:remote -a foo-server`
- `$ git remote`
    - >  heroku
- I'm going to push here.
    - `$ git push --set-upstream heroku master`
    - I can push, but build fails.
- `$ pip install gunicorn`
- `$ pip freeze > requirements.txt`
- create "Procfile"
:

```
web: gunicorn server:"create_app()"
```

    - name "server" points the module on "./server"
- `$ heroku config:set FLASK_APP=server`
- add and commit
- `$ git push heroku master`
    - Make sure the build is successful
- `$ heroku open`
    - Open it in your browser and make sure it says OK.

Implement the required API
- View the build log when pushing and the error log when accessing
    - `$ heroku logs --tail`
    - You forgot to include the necessary files, and you get a runtime error when accessing the system.
    - Or error at build time: [mecab no such file or directory: /usr/local/etc/mecabrc [https://medium.com/@jiraffestaff/mecabrc-%E3%81%8C%E8%A6%8B%E3](https://medium.com/@jiraffestaff/mecabrc-%E3%81%8C%E8%A6%8B%E3) 81%A4%E3%81%8B%E3%82%89%E3%81%AA%E3%81%84%E3%81%84%E3%81%86%E3%82%A8%E3%83%A9%E3%83%BC-b3e278e9ed07]
- `By default, a route only answers to GET requests.`[doc](https://flask.palletsprojects.com/en/2.0.x/quickstart/#http-methods)
    - `@app.route('/', methods=['GET', 'POST'])`
- JSON
    - `property json: Optional[Any]` [doc: Incoming Request Data](https://flask.palletsprojects.com/en/2.0.x/api/#incoming-request-data)
        - > The parsed JSON data if mimetype indicates JSON (application/json, see is_json).
- If you call from other origins: [[Flask-CORS]] is required

"No web processes running"
- I typo'd the file name in the Procfile.
- The build itself goes through...


----old memo
[[Heroku+Flask 2019-6-07 memo]]
---
This page is auto-translated from [/nishio/Heroku+Flask](https://scrapbox.io/nishio/Heroku+Flask) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.