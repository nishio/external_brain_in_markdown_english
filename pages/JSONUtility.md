---
title: "JSONUtility"
---

Passing a Vector3 Array to ToJson will result in `{}`.
> passing an array to this method will not produce a JSON array containing each element
[https://docs.unity3d.com/ScriptReference/JsonUtility.ToJson.html](https://docs.unity3d.com/ScriptReference/JsonUtility.ToJson.html)

You cannot [[serialize]] an Array directly, but you can serialize an instance of a class that has an Array as a field.

When I try to JsonUtil.FromJson<Foo> it fails to compile. FromJsonOverwrite(json, foo) on a previously created Foo instance foo succeeds.

Trap where property getter seems not to be called during serialization.
- explicitly call

[[Unity]]

---
This page is auto-translated from [/nishio/JSONUtility](https://scrapbox.io/nishio/JSONUtility) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.