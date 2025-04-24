---
title: "Minecraft Pi Socket API"
---

![image](https://gyazo.com/d82a2610de7f71191303b86b6bc97399/thumb/1000)
Minecraft: Pi edition can send packets via TCP to place blocks at arbitrary coordinates
- On the client side, there is a Python library [[mcpi]].
- A plugin that adds this protocol to Bukkit-based servers is [[RaspberryJuice]].

[[mcpi]]: Python library for communicating with Minecraft: Pi edition and RaspberryJuice.
[https://github.com/martinohanlon/mcpi](https://github.com/martinohanlon/mcpi)
API REFERENCE [https://www.stuffaboutcode.com/p/minecraft-api-reference.html](https://www.stuffaboutcode.com/p/minecraft-api-reference.html)

[[RaspberryJuice]]: A Bukkit plugin which implements the Minecraft Pi Socket API.
[https://github.com/zhuowei/RaspberryJuice](https://github.com/zhuowei/RaspberryJuice)
- [https://www.spigotmc.org/resources/raspberryjuice.22724/](https://www.spigotmc.org/resources/raspberryjuice.22724/)

python

```
from mcpi import minecraft
m = minecraft.Minecraft.create(SERVER_IP_ADDRESS, 4711)
m.setBlock([X, Y, Z, ID])
```


I was confused because the default settings were relative coordinates from the spawn point, so the blocks were not created where I expected them to be.
It was necessary to change the configuration file created at the first startup and restart the system.

python

```
from mcpi import block
m.setBlock(0, 80, 0, block.STONE.id)
```

![image](https://gyazo.com/6dc5f0c700922eb6af0eca2e6bb0e433/thumb/1000)

python

```
m.setBlocks(0, 80, 0, 15, 80, 15, block.STONE.id)
```

![image](https://gyazo.com/7d0577698a7571c3a3d0db82e482d355/thumb/1000)

python

```
m.setBlocks(0, 80, 0, 512, 80, 512, block.STONE.id)
```

![image](https://gyazo.com/9c9e7e6ae2220d4dea255f2ecec3d2f3/thumb/1000)

python

```
for x in range(30):
	for z in range(30):
		m.setBlock(x, 81, z, block.WOOL.id, x * z % 16)
```

![image](https://gyazo.com/d82a2610de7f71191303b86b6bc97399/thumb/1000)

---
This page is auto-translated from [/nishio/Minecraft Pi Socket API](https://scrapbox.io/nishio/Minecraft Pi Socket API) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.