---
title: "I want to prevent the brightness from changing depending on the panel orientation."
---

![image](https://gyazo.com/fafd1201d223da5a49026cc1d8486d37/thumb/1000)

    - [[Always make them look at you.]] now changes the orientation of the slides, but the result is too bright to read or too dark.
- ![image](https://gyazo.com/b4fc98c314302a46476e2f4d1f1649fe/thumb/1000)

    - I heard that [[shader]] should be set to [[Unlit/Texture]].
cs

```cs
obj.GetComponent<Renderer>().material.shader = Shader.Find("Unlit/Texture");
```


- This alone [[turn magenta]].
    - If you specify a Unlit/Texture shader dynamically from a script, it will be assumed to be a shader that is not in use at compile time and will be deleted. To avoid this, put the material that uses the shader under Resources.

- I want to make sure that the brightness does not change depending on the orientation of the slide.

---
This page is auto-translated from [/nishio/パネルの向きで明るさが変わらなくしたい](https://scrapbox.io/nishio/パネルの向きで明るさが変わらなくしたい) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.