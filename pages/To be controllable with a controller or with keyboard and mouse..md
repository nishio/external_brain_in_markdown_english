---
title: "To be controllable with a controller or with keyboard and mouse."
---

Since it takes time to install the software on the Oculus for each experiment, basic operations can be tested on a PC that is not connected to the controller.

Camera rotation with keyboard
cs

```cs
void Update () {
       if (Input.GetKey(KeyCode.UpArrow))
       {
           camera.transform.Rotate(camera.transform.right, -1f);
       }
       if (Input.GetKey(KeyCode.DownArrow))
       {
           camera.transform.Rotate(camera.transform.right, 1f);
       }
       if (Input.GetKey(KeyCode.LeftArrow))
       {
           camera.transform.Rotate(camera.transform.up, -1f);
       }
       if (Input.GetKey(KeyCode.RightArrow))
       {
           camera.transform.Rotate(camera.transform.up, 1f);
       }
   }
```


Raycasting with both mouse and controller
cs

```cs
if (Input.mousePresent)
{
    // PC Mode
    ray = Camera.main.ScreenPointToRay(Input.mousePosition);
}
else
{
    // Oculus Mode
    ray = new Ray(pointer.position, pointer.forward);
}
```

Where we used to use pointer.position and pointer.forward, we now use ray.origin and ray.forward.

Make it responsive to both controller triggers and mouse right clicks.
cs

```cs
if (OVRInput.GetDown(OVRInput.Button.PrimaryIndexTrigger) || Input.GetMouseButton(0))
```

I created the following static method because it is tedious to go around writing the above every time.
cs

```cs
public static bool Up()
{
    return OVRInput.GetUp(OVRInput.Button.PrimaryIndexTrigger) || Input.GetMouseButtonUp(0);
}
```

Keyboard will be assigned to swipes, etc. as appropriate in the future.
Should we make a key config setting screen if we want to get serious?
Page Up/Down
Shift+Page Up/Down


---
This page is auto-translated from [/nishio/コントローラでもキーボードとマウスでも操作できるように](https://scrapbox.io/nishio/コントローラでもキーボードとマウスでも操作できるように) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.