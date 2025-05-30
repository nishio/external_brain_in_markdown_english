---
title: "Save and Load"
---

- Unity has a standard load/save function called [[PlayerPrefs]].
    - It accepts only basic types such as integers and strings.
- There is also [[JSONUtility]] as a standard feature
- So complex types should be converted to strings with JSONUtility.ToJson() and stored in PlayerPrefs
- But JsonUtil has a trap.
    - Unity's JSONUtility serializes List<Vector3> to {}
        - Valid as JSON so it can be read/written with FromUtility<List<Vector3>>, but null reference error because the content is empty
    - In the first place, you can't serialize a List, let alone an Array.
    - Specifications.
    - Cannot serialize an Array directly, but can serialize an instance of a class that has an Array as a field
    - JsonUtil.ToJson of class Foo with Vector3[] as a field succeeds, but JsonUtil.FromJson<Foo> fails to compile because the compiler does not understand how to convert to Foo.
        - FromJsonOverwrite(json, foo) on a previously created Foo instance foo will succeed.
- I thought I could create a proxy class to mediate information, and collect and distribute information with getter/setter of properties, but it seems that getter/setter is not called during serialization, so I decided to call it explicitly.
cs

```cs
public class SlidePositionProxy : MonoBehaviour {
    public void BeforeGet()
    {
        Debug.Log("BeforeGet");
        var slides = GameObject.Find("MotherMonolith").GetComponent<MakeSlides>().slides;
        Debug.Log(slides.Count);
        var positions = new Vector3[slides.Count];
        for (int i = 0; i < slides.Count; i++)
        {
            positions[i] = slides[i].transform.position;
        }
        Positions = positions;
    }
    public void AfterSet()
    {
        Debug.Log("AfterSet");
        var slides = GameObject.Find("MotherMonolith").GetComponent<MakeSlides>().slides;
        for (int i = 0; i < slides.Count; i++)
        {
            slides[i].transform.position = Positions[i];
        }
    }

    [SerializeField]
    public Vector3[] Positions;
}

```


---
This page is auto-translated from [/nishio/セーブとロード](https://scrapbox.io/nishio/セーブとロード) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.