---
title: "Dynamic creation of objects"
---

- `[SerializeField] GameObject sceneObject;`
    - Go to the [[SerializeField]] setting UI and drop the object you want to duplicate there.
- `var obj = GameObject.Instantiate(sceneObject);`
    - Duplicated by [Instantiate
- Note: If you put this script in the object you want to duplicate, the object will be duplicated (BOMB) with the entire script.
    - [[Create Empty]] and put a script in it.

---
This page is auto-translated from [/nishio/オブジェクトの動的生成](https://scrapbox.io/nishio/オブジェクトの動的生成) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.