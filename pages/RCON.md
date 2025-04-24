---
title: "RCON"
---

> RCON is a protocol that allows server administrators to remotely execute Minecraft commands.
[https://wiki.vg/RCON](https://wiki.vg/RCON)

Python
[https://github.com/barneygale/MCRcon](https://github.com/barneygale/MCRcon)
- This doesn't seem to be behaving properly.

mcrcon works fine.

[Iapetus-11/aio-mc-rcon: An asynchronous RCON client/wrapper for Minecraft Java Edition](https://github.com/Iapetus-11/aio-mc-rcon)
- `$ pip install aio-mc-rcon`
python

```
from aiomcrcon import Client
import asyncio

async def main():
    command = "hd setLine test 1 Hello World via RCON"

    client = Client(HOST, PORT, PASSWORD)
    await client.connect()

    response = await client.send_cmd(command)
    print(response)

    await client.close()


if __name__ == "__main__":
    asyncio.run(main())
```

![image](https://gyazo.com/3f8b05fedbd5995d286f344fcdff6a06/thumb/1000)

---
This page is auto-translated from [/nishio/RCON](https://scrapbox.io/nishio/RCON) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.