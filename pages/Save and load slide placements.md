---
title: "Save and load slide placements"
---

[https://youtu.be/rkuv1eEkwC0](https://youtu.be/rkuv1eEkwC0)
- Convert `Vector3[]` to string using [[JSONUtility]] and save it in [[PlayerPrefs]].





-----

- [[curbing (e.g. a file)]]
- I don't want to deal with [Unity - Scripting API: File](https://docs.unity3d.com/ScriptReference/Windows.File.html) in raw
- IL2CPP, using LitJson is old since Unity can handle JSON as standard
    - [https://docs.unity3d.com/ScriptReference/JsonUtility.html](https://docs.unity3d.com/ScriptReference/JsonUtility.html)
- [[PlayerPrefs]] looks good.
    - [https://docs.unity3d.com/ScriptReference/PlayerPrefs.html](https://docs.unity3d.com/ScriptReference/PlayerPrefs.html)

-----
- How do you do file read/write?
- Should I read and write in JSON?
- Where are files saved when read/write on Oculus Go?

This is a more chewed up version of this that I had previously written
> I want to hit the Scrapbox API to get Lines, make them into Draggable objects and place them in the scene.
>  I want to save the edited result on Unity on the net and restore it later.


---
This page is auto-translated from [/nishio/スライドの配置のセーブ・ロード](https://scrapbox.io/nishio/スライドの配置のセーブ・ロード) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.