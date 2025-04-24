---
title: "How to create a Unity project"
---

- First time only [Setting up Android Development Environment](https://docs.unity3d.com/Manual/android-sdksetup.html)
- First time only [Create Organization](https://dashboard.oculus.com/)
- Create 3D projects
- First time only [[External Tools]] settings
- [Under "Build Settings," set "Platform" to Android.
    - ![image](https://gyazo.com/8e9d7d6ec503d50e7954f59415439edb/thumb/1000)

- [[Edit]] > [[Project Settings]] > [[Player]] > [[XR Settings]]
    - Supported = True
    - SDK = Oculus
    - I don't know about the rest.
    - ![image](https://gyazo.com/db0d75642a085b2a48d9e9dad184b1ef/thumb/1000)
    - Forgetting this = [[I don't get binocular vision.]].

- Other Settings
    - Package Name
    - Minimum API Level=7.1
    - ![image](https://gyazo.com/e9099415897ef7ce54489b4de304770f/thumb/1000)

- Personal.
    - Put something different around (0, 0, 100)
        - I can see which project it is when I look back at screenshots, etc. later.
        - ![image](https://gyazo.com/f43d85e9c0cc0ccdbef6bc27f30a7298/thumb/1000)
        - Also [[mother monolith]].
- At this point, Build & Run to confirm that the scene looks as expected above.

- Project Location
    - I was wondering why I couldn't find it, but somehow it was here.
        - `C:\Users\Public\Documents\Unity Projects`

- Enter [Oculus Utilities for Unity
    - [https://developer.oculus.com/downloads/package/oculus-utilities-for-unity-5/](https://developer.oculus.com/downloads/package/oculus-utilities-for-unity-5/)
    - Download and extract the file and put it in the Assets folder.
    - Or search for Oculus Integration in the Assets Store and put it in.
    - Oculus > VR > Prefabs
        - When [[OVRPlayerController]] is added, a [[Collider]] with physics is created and the camera becomes a child of it, so if there is no ground, it will fall.
        - <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>is not the type of game you want to make that moves around the map, so add [[OVRCameraRig]] directly.
        - Put [[TrackedRemote]] in LeftHandAnchor, RightHandAnchor
    - If you go this far, the camera should move with the direction of your head, and the orientation and rotation of the remote control should also be reflected.

-----
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Notes on the experience of
- one-eyed
    - The ground was made into a regular Cube.
        - [[Choosing Things with Laser Pointers]]
    - When I zoomed in, for some reason the ground moved depending on the camera's orientation.
- Second.
    - When I made the ground with [[Terrain]], it took a long time to build for writing to Oculus.
    - Deleted, but not once created?
        - [[Ground not required]]
        - [[Automatic slide movement]]
    - I tried to use Unity-chan as my avatar.
            - [[Unity's first-person view]]
- The third one ← here and now

---
This page is auto-translated from [/nishio/Unityプロジェクトの作り方](https://scrapbox.io/nishio/Unityプロジェクトの作り方) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.