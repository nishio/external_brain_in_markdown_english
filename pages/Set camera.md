---
title: "Set camera"
---

There are many explanations out there that tell you to set the SerializeField by dragging and dropping it on the UI, but if you know that there is only one OVRCameraRig in the scene, you can find it, and if there is only one main camera in the scene to begin with, you can just use [[Camera. main]]. main] is fine if there is only one camera in the scene.

cs

```cs
    [SerializeField]
    GameObject camera;

	void Start () {
        if (!camera)
        {
            camera = GameObject.Find("OVRCameraRig");
        }
	}

```


It is a waste of time to reuse a script, forget to set a reference to a field, and then die at runtime with an exception.

[[GameObject.Find]]

---
This page is auto-translated from [/nishio/カメラをセット](https://scrapbox.io/nishio/カメラをセット) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.