---
title: "Viewpoint cannot be shifted."
---

We set up a sphere called a teleport portal that jumps to it when it is triggered.
cs

```cs
GameObject.Find("OVRCameraRig").transform.position = obj.transform.position;
```

Viewpoint can be moved on PC but not on Oculus

I thought it might be wrong to run OVRCameraRig directly, so I specified OVRCameraRig as a child of a cube called MeCube, but it still does not work.

Interesting bugs
[https://youtu.be/LwDUS8wMFAE](https://youtu.be/LwDUS8wMFAE)
- When MeCube is triggered, it is treated as a slide and the position of the object moves to the [[hitPoint]] of the raycast, causing MeCube to move and the camera to move accordingly.
- So, moving the camera by moving the MeCube itself is working as expected.

cs

```cs
RaycastHit hit;
if (Physics.Raycast(ray, out hit, _MaxDistance))
{
    // Get the object that was hit
    GameObject obj = hit.collider.gameObject;
    obj.GetComponent<Renderer>().material.color = Color.green;
    if (obj.CompareTag("Button"))
    {
    	   ...
    }
    else if(obj.CompareTag("Teleport"))
    {
        obj.GetComponent<Renderer>().material.color = Color.blue;
        if (PCInput.Down())
        {
            obj.GetComponent<Renderer>().material.color = Color.red;
            //GameObject.Find("OVRCameraRig").transform.position = obj.transform.position;
            GameObject.Find("MeCube").transform.position = obj.transform.position;
        }
    }
```


- It is strange that it is green on Oculus.
- But how is such "tag behavior different between PC and Android" possible?
- Is it wrong that I once created a Teleport named Tereport and deleted it?
- Try restarting Unity.
- Fixed!
    - [[Restart Unity after deleting tags.]]
#Resolved

---
This page is auto-translated from [/nishio/視点移動ができない](https://scrapbox.io/nishio/視点移動ができない) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.