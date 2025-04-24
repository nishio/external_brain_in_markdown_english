---
title: "Always make them look at you."
---

![image](https://gyazo.com/b4fc98c314302a46476e2f4d1f1649fe/thumb/1000)

- You can easily make it with [[Quaternion.LookRotation]].
:

```
for(int i = 0; i < slides.Count; i++)
{
    GameObject obj = slides[i] as GameObject;
    Vector3 relativePos = obj.transform.position - camera.transform.position;
    Quaternion rotation = Quaternion.LookRotation(relativePos, camera.transform.up);
    obj.transform.rotation = rotation;
}
```


---
This page is auto-translated from [/nishio/常にこちらを向かせる](https://scrapbox.io/nishio/常にこちらを向かせる) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.