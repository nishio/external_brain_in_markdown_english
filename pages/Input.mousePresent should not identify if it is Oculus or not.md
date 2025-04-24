---
title: "Input.mousePresent should not identify if it is Oculus or not"
---

Unity's [[Input.mousePresent]] was always False under Oculus environment, but it was initially False but changed to True after triggering. don't use mouse presence or absence to distinguish between PC and Oculus environment. I'm not sure if it's a PC environment or an Oculus environment.

So here's how it turned out:.
cs

```cs
public static bool isOculus()
{
    return (
        OVRInput.GetActiveController() == OVRInput.Controller.RTrackedRemote ||
        OVRInput.GetActiveController() == OVRInput.Controller.LTrackedRemote);
}
```



---
This page is auto-translated from [/nishio/Input.mousePresentでOculusかどうか識別してはいけない](https://scrapbox.io/nishio/Input.mousePresentでOculusかどうか識別してはいけない) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.