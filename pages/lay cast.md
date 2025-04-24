---
title: "lay cast"
---

- Straight line ([[ray]]) and [[collider]] hit detection
- Note that it is not the mesh that is displayed, but only the collider and the collider.
- It may be possible to set a filter to respond only to certain colliders
- MeshCollider must be Convex
- If a ray is flown from a vertex on the MeshCollider, it will hit

cs

```cs
Ray pointerRay = new Ray(pointer.position, pointer.forward);
RaycastHit hitInfo;
if (Physics.Raycast(pointerRay, out hitInfo, _MaxDistance))
{
    GameObject obj = hitInfo.collider.gameObject;
```

[[Physics.Raycast]]

[https://docs.unity3d.com/ja/current/ScriptReference/Physics.Raycast.html](https://docs.unity3d.com/ja/current/ScriptReference/Physics.Raycast.html)


---
This page is auto-translated from [/nishio/レイキャスト](https://scrapbox.io/nishio/レイキャスト) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.