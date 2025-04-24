---
title: "turn magenta"
---

![image](https://gyazo.com/dcc56923cb9a65ff936094dcb3ebd6fd/thumb/1000)
This case
- Phenomenon: I specified a shader from a script and it looked fine on the PC, but on the Oculus Go it turned magenta.
- cause
    - Specify [[Unlit/Texture]] shader using [[Shader.Find]] from script
    - But the Unity compiler does not know that it is referenced in Shader.Find
    - So, they decide "it's a shader we're not using" and remove it from the Oculus Go version.
- cope
    - Anything under [[Resources]] is considered to be a [[dynamic load]] target, and it and anything referenced from it are not deleted.
    - Then, create an appropriate material under Resources and specify Unlit/Texture.

---
This page is auto-translated from [/nishio/マゼンタになる](https://scrapbox.io/nishio/マゼンタになる) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.