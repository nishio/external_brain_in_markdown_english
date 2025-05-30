---
title: "Unity's standard VR support features"
---

Q: What do I need to do to get to the point where I can view a virtual space in which I have set up my own model in oculus go? Our 3D knowledge stops at Metaseko. [Facebook](https://www.facebook.com/nishiohirokazu/posts/10215457336603119)

A:
1. make models in Blender, etc. (or charge a 3D company)
2. turn on the developer mode of Oculus Go (in the process, register as a development organization)
3. set up [[Unity]] to build Android apps and enable Oculus with XR support
Import the model into Unity and place the main camera
Connect Oculus Go to PC, Build and Run

Reference for steps 2 and 3
[http://www.yoshidayo.com/entry/2018/05/09/103503](http://www.yoshidayo.com/entry/2018/05/09/103503)
- As of 2018-06-04, I was told there is no API Level 25, so I set Target to 27.
- I got a build and saw something.
- I don't know how to exit.

- I don't know how to place objects.
    - I'm not even sure if I'm seeing things correctly if I can't put things down.
        - [[Layout in Unity]]  [http://www.atmarkit.co.jp/ait/articles/1410/27/news037_3.html](http://www.atmarkit.co.jp/ait/articles/1410/27/news037_3.html)
    - You can do it by pressing Create from Hierarchy and doing it properly.
        - [http://www.atmarkit.co.jp/ait/articles/1411/06/news040.html](http://www.atmarkit.co.jp/ait/articles/1411/06/news040.html)
- I don't know how to keep fbx files of objects
    - [https://docs.unity3d.com/jp/460/Manual/HOWTO-importObject.html](https://docs.unity3d.com/jp/460/Manual/HOWTO-importObject.html)
    - They say you can put it in the project folder.
    - Or drag and drop.

- Enter [Oculus Utilities for Unity
    - [https://developer.oculus.com/downloads/package/oculus-utilities-for-unity-5/](https://developer.oculus.com/downloads/package/oculus-utilities-for-unity-5/)
    - Download and extract the file and put it in the Assets folder.


Q: Do I have to write the implementation so that the camera moves according to the operation...

A:
Unity's standard VR support feature allows the camera in the scene to shake its head on its own (without writing any code).
For more detailed settings or to display the controller model in the scene, drop down [[Oculus Integration]] from the AssetStore and use [[OVRCameraRig]] or [[TrackedRemote prefab]].



---
This page is auto-translated from [/nishio/Unityの標準のVRサポート機能](https://scrapbox.io/nishio/Unityの標準のVRサポート機能) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.