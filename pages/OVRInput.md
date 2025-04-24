---
title: "OVRInput"
---

[https://developer.oculus.com/documentation/unity/latest/concepts/unity-ovrinput/](https://developer.oculus.com/documentation/unity/latest/concepts/unity-ovrinput/)
> To use OVRInput, you must either:
- >  Include an instance of [[OVRManger]] anywhere in your scene; or
- >  Call OVRInput.Update() and OVRInput.FixedUpdate() once per frame at the beginning of any component’s Update and FixedUpdate methods, respectively.
But when I tried to drag-drop OVRManager onto Scene, it was NG.
Isn't this it?
![image](https://gyazo.com/9a5ce7224c7dcefda7043dccd79b5400/thumb/1000)

It seems like it should be added as a component of some object (like [[mother monolith]]), not a scene?

---
This page is auto-translated from [/nishio/OVRInput](https://scrapbox.io/nishio/OVRInput) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.