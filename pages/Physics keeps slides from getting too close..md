---
title: "Physics keeps slides from getting too close."
---

from  [[Improved physics]]

    - Phenomenon of slides approaching in [[physical operation]].
    - In the first place, it's not right to get close to the slides, because if the physics happens, it means the slides are crowded and colliding.
    - This is why I stayed away from it. Like this
cs

```cs
// update position
for (int i = 0; i < slides.Count; i++)
{
    GameObject obj = slides[i] as GameObject;
    // current position and distance
    Vector3 cpos = obj.transform.position;
    float cdist = (cpos - eye).magnitude;
    // next position and distance
    Vector3 npos = cpos + updateVec[obj];
    float ndist = (npos - eye).magnitude;
    if(ndist < cdist)
    {
        npos = eye + (npos - eye).normalized * cdist;
    }
    obj.transform.position = npos;
}
```



---
This page is auto-translated from [/nishio/物理演算でスライドを近寄らせない](https://scrapbox.io/nishio/物理演算でスライドを近寄らせない) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.