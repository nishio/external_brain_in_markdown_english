---
title: "GameObject.Find"
---

cs

```cs
GameObject.Find("Hand");
```

[Unity - Scripting API: GameObject.Find](https://docs.unity3d.com/ScriptReference/GameObject.Find.html)

- Pull [[mother monolith]] by name and access child components from there, etc.
cs

```cs
var slides = GameObject.Find("t").GetComponent<MakeSlides>().slides;
```


---
This page is auto-translated from [/nishio/GameObject.Find](https://scrapbox.io/nishio/GameObject.Find) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.