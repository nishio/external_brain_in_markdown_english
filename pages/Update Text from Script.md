---
title: "Update Text from Script"
---

![image](https://gyazo.com/ecfc18d06bb92fd64db60ba69102ee49/thumb/1000)

cs

```cs
GameObject.Find("FooText").GetComponent<Text>().text = x.ToString();
```

If the text itself has a unique name "FooText".

I tried to cast Text after getting [[GameObject]] in Find, but that was a mistake.

If the parent object that has the text has a name
cs

```cs
GameObject.Find("Foo").GetComponentInChildren<Text>().text = x.ToString();
```


- Update [[Text]] from script
    - [[debug]]

---
This page is auto-translated from [/nishio/スクリプトからTextを更新](https://scrapbox.io/nishio/スクリプトからTextを更新) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.