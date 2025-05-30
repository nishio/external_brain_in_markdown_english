---
title: "Unity's first-person view"
---

- If the camera offset is (0, 1.4, 0.05), you can naturally see your own chest when looking down.
    - ![image](https://gyazo.com/cf067db791e294d5772cc76529728de9/thumb/1000)
    - I first noticed you wearing the Unity mark accessory.
    - This position is rather comfortable in relation to the arms, which are visible when you turn your head to the side.
    - ![image](https://gyazo.com/dd1704ce84b8198e6e08864baf4c8ba8/thumb/1000)
    - But if you look down very low, you can see inside your body.
        - In fact, it's already wedged into the body, and the head is too close to the camera to see the back side due to objects not being rendered.
        - Is there an option to not draw backside polygons in the first place?
    - When I turn my head to the side, my hair comes into view.
    - In the meantime, I tried to Disable anything that might interfere.
        - ![image](https://gyazo.com/ace60de05f561095393a4df519fe8740/thumb/1000)


- In fact, the facial bones should rotate as the camera direction moves.
- (0, 1.4, 0.15), it doesn't get stuck when you look down, but you can see the tip of the toes, which is a bit discomforting.


---
This page is auto-translated from [/nishio/Unityちゃんの一人称視点](https://scrapbox.io/nishio/Unityちゃんの一人称視点) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.