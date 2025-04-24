---
title: "Flask Blueprint"
---

python

```
from flask import Flask, Blueprint

bp = Blueprint('server', __name__)


def create_app():
    app = Flask(__name__)
    app.register_blueprint(bp)
    return app


@bp.route('/', methods=['GET'])
def root():
    return "OK"
```


It is minimalistic to do routing in app.route, but it is difficult to do when you want to separate files, so create a blueprint and add it to the app later.

---
This page is auto-translated from [/nishio/Flask Blueprint](https://scrapbox.io/nishio/Flask Blueprint) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.