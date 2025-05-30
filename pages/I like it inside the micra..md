---
title: "I like it inside the micra."
---

It's done.
[https://youtu.be/x85oTw5-ZGg](https://youtu.be/x85oTw5-ZGg)

structure
- button, the command block executes `webhooks execute post-like x` (the x part is an arbitrary name)
- [[SimpleWebhooks]] POSTs name to `http://localhost:5000/`.
- Flask running on localhost receives request and executes command with [RCON
    - `command = f"data get storage likes {name}"`
        - Get the number of likes from [storage
        - increase by one
    - `command = f"data modify storage likes {name} set value {value}"`
        - Write the increased value to storage
    - `command = f"hd setLine likes_{name} 1 LIKE: {value}"`
        - Updated [Holographic Displays
        - Assuming the name of the HD is in the form `likes_x`.


SimpleWebhooks/config.yaml

```yaml
post-like:
  url: http://localhost:5000/
  json:
    name: "{COMMAND_PARAM_1}"
```


server.py

```
from flask import Flask, request
from aiomcrcon import Client
import asyncio
import re
import threading
from secret import PASSWORD, HOST, PORT

app = Flask(__name__)
client = Client(HOST, PORT, PASSWORD)


def create_app():
    return app


async def update_likes(name):
    await client.connect()

    command = f"data get storage likes {name}"
    response = await client.send_cmd(command)
    if "Found no elements matching" in response[0]:
        value = 0
    else:
        value = int(re.search("\d+", response[0]).group())

    value += 1
    command = f"data modify storage likes {name} set value {value}"
    response = await client.send_cmd(command)

    command = f"hd setLine likes_{name} 1 LIKE: {value}"
    response = await client.send_cmd(command)
    
    await client.close()


@app.route('/', methods=['GET', 'POST'])
def root():
    if request.method == "GET":
        return "OK"
    else:
        name = request.json["name"]

    x = threading.Thread(target=lambda: asyncio.run(update_likes(name)), args=()).start()
    return "OK"
```


place to get stuck in
- Need to return OK before executing RCON against webhook
    - Sending a RCON packet but it is not executed and times out
    - Perhaps the webhook command is grabbing a lock.
    - So I decided to create a form of thread.

mimicry
- VirtualPersents like feature
    - ![image](https://gyazo.com/d9056b3fc37945d0d7b84cb579fccd2e/thumb/1000)
    - [https://jr.mitou.org/projects/2019/virtual_presents](https://jr.mitou.org/projects/2019/virtual_presents)
    - [[Death Landing]]

---
This page is auto-translated from [/nishio/マイクラ内でいいね](https://scrapbox.io/nishio/マイクラ内でいいね) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.