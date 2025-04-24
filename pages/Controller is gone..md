---
title: "Controller is gone."
---

- We've had both the main camera and the [[OVRCameraRig]] camera.
    - The location was a little off.
- Delete the main camera after adding OVRCameraRig, as it should be removed.
- Controller is gone.
- Cause: The coordinates of the controller are at the exact same position as the OVRCameraRig camera, so it is not visible.
    - Move it to the appropriate position in Scene, and the controller will appear on the screen in Game.
    - (0.2, -0.2, 0.5).
    - I didn't realize it was because of the camera change because the two cameras were looking in the same direction.

---
This page is auto-translated from [/nishio/コントローラが消えた](https://scrapbox.io/nishio/コントローラが消えた) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.