---
title: "LELIEL"
---

![image](https://gyazo.com/227e09f357758240a4f0893a56c42161/thumb/1000)
mimicry
- Enemies in Neon Genesis Evangelion
- [https://evangelion.fandom.com/wiki/Leliel](https://evangelion.fandom.com/wiki/Leliel)
- > Leriel appears to be a floating sphere with a distorted black and white color pattern that suddenly appears in the sky above the three wards of Tokyo. However, Leliel's entity is actually a shadow that appears on the ground. Leliel's body in our dimension is 680 meters wide and 3 nanometers thick, and the sphere is merely its "shadow.

basic policy
- We have a beautiful material image, so we use this as the original data and generate it programmatically.
    - ![image](https://gyazo.com/c310b7f3146c6cb0dfd69dd38f99d85c/thumb/1000)
    - [https://evangelion.fandom.com/wiki/Leliel](https://evangelion.fandom.com/wiki/Leliel)
- Find a point in two dimensions when it is projected from the viewpoint and the coordinates to place it.
    - Obtaining color from a material image
    - Placement of blocks with [mcpi

python

```
import numpy as np
import skimage.io
from mcpi import minecraft
from math import sqrt

# viewpoint
vp = np.array([6009.50, 80.00 + 1.5, 2.50])
# target
tp = np.array([6110, 150, -80])

cam_y = tp - vp
cam_y = cam_y / np.linalg.norm(cam_y)
cam_x = np.cross(cam_y, np.array([0, 1, 0]))
cam_x = cam_x / np.linalg.norm(cam_x)
cam_z = np.cross(cam_x, cam_y)

image = skimage.io.imread(f'/Users/nishio/Documents/leliel.png')
assert image.shape == (400, 400, 4)


def get_color(x, y, z):
    tp = np.array([x, y, z])
    d = tp - vp
    scale = 4.5
    down = np.dot(d, cam_z) * -scale + 200
    left = np.dot(d, cam_x) * scale + 200
    rgba = image[int(down), int(left)]
    if rgba[3] == 0:
        raise RuntimeError("transparent")
    if rgba[0] < 128:
        return BLACK
    return WHITE


RADIUS = 40
m = minecraft.Minecraft.create(HOST, PORT)
cx, cy, cz = tp
WOOL = 35
WHITE = 0
BLACK = 15
THICKNESS = 1.74  # larger than sqrt(3)
x, y, z = tp
for dx in range(-RADIUS, RADIUS + 1):
    x = cx + dx
    for dy in range(-RADIUS, RADIUS + 1):
        y = cy + dy
        for dz in range(-RADIUS, RADIUS + 1):
            z = cz + dz
            if abs(RADIUS - sqrt(dx ** 2 + dy ** 2 + dz ** 2)) < THICKNESS:
                m.setBlock([x, y, z, WOOL, get_color(x, y, z)])
```


I'm projecting a 2D image onto a sphere in the micro-world.
- ![image](https://gyazo.com/cfc9f423a4014242cc891598d13acbd8/thumb/1000)
It's so cunning.
- ![image](https://gyazo.com/ed7f2a433cd7ee8ca641dd1596bf98dd/thumb/1000)
The world is covered in darkness.
- ![image](https://gyazo.com/d2289d068169d7ee7720699dbca93a39/thumb/1000)


[https://youtu.be/2ZsXJLJb6uI](https://youtu.be/2ZsXJLJb6uI)

I know how long it takes to rewrite.
- I thought about making a video shoot of the rewrite of the gun because it was interesting, but when I checked the original, it was more like it moved slowly and then suddenly came to the sky, rather than rewrite.

---
This page is auto-translated from [/nishio/LELIEL](https://scrapbox.io/nishio/LELIEL) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.