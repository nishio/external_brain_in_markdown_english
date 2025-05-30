---
title: "Server Resource Pack Trial and Error Log"
---

from  [[Creating Resource Packs in Minecraft JE1.17]]
Server Resource Pack Trial and Error Log
(Note: The following is incorrect)
:

```
resourcepacks$ zip -r cybozu.zip cybozu
updating: cybozu/ (stored 0%)
  adding: cybozu/assets/ (stored 0%)
  adding: cybozu/assets/minecraft/ (stored 0%)
  adding: cybozu/assets/minecraft/textures/ (stored 0%)
  adding: cybozu/assets/minecraft/textures/block/ (stored 0%)
  adding: cybozu/assets/minecraft/textures/block/yellow_glazed_terracotta.png (deflated 5%)
  adding: cybozu/pack.mcmeta (deflated 16%)
```


`[11:29:23] [Server thread/WARN]: You specified a resource pack without providing a sha1 hash. Pack will be updated on the client only if you change the name of the pack.`
If you don't specify the sha1 hash, you won't be able to update it, and that's a problem.

`$ sha1sum cybozu.zip `
`3170755eaf87fc4b8a32bd88dfa77c65af3f9aad  cybozu.zip`

server

```
require-resource-pack=true
resource-pack=https\://www.dropbox.com/s/6h9150qaf93hdun/cybozu.zip?dl\=1
resource-pack-sha1=3170755eaf87fc4b8a32bd88dfa77c65af3f9aad
```

![image](https://gyazo.com/7fc373ec09ddd8769e60ce35f6195fe4/thumb/1000)

![image](https://gyazo.com/dfd121a0522b263df05674717f980b80/thumb/1000)
Huh?

Like this?
:

```
cybozu$ zip -r ../cybozu.zip .
  adding: assets/ (stored 0%)
  adding: assets/minecraft/ (stored 0%)
  adding: assets/minecraft/textures/ (stored 0%)
  adding: assets/minecraft/textures/block/ (stored 0%)
  adding: assets/minecraft/textures/block/yellow_glazed_terracotta.png (deflated 5%)
  adding: pack.mcmeta (deflated 16%)
```


It downloads correctly, but the picture hasn't changed.
Oh, okay, I get it, you want to change the `minecraft:` in this to `cybozu:`.
- Note: The description here may not be correct, I will check and correct it later.
:

```
{
  "variants": {
    "facing=east": {
      "model": "minecraft:block/yellow_glazed_terracotta",
      "y": 270
    },
...
}
```

It's done, it's done, it's done.

---
This page is auto-translated from [/nishio/サーバリソースパック試行錯誤ログ](https://scrapbox.io/nishio/サーバリソースパック試行錯誤ログ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.