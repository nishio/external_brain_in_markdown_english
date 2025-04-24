---
title: "Convert from local to world coordinate system"
---

[[Transform.TransformPoint]]
cs

```cs
public Vector3 TransformPoint(Vector3 position);
```


> Transforms position from local space to world space.
> Note that the returned position is affected by scale. Use [[Transform.TransformDirection]] if you are dealing with direction vectors.
> You can perform the opposite conversion, from world to local space using [[Transform.InverseTransformPoint]].
[https://docs.unity3d.com/ScriptReference/Transform.TransformPoint.html](https://docs.unity3d.com/ScriptReference/Transform.TransformPoint.html)

- Convert from [[local coordinate system]] to [world coordinate system
[[Transform]]

---
This page is auto-translated from [/nishio/ローカル座標系からワールド座標系に変換](https://scrapbox.io/nishio/ローカル座標系からワールド座標系に変換) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.