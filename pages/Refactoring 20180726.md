---
title: "Refactoring 20180726"
---

- Initially the slides were GameObjects.
    - Managed by `AttayList<GameObject> slides`.
    - In implementing physics, I created an update vector with `Dictionary<GameObject, Vector3> updateVec`.
    - For red box highlighting, I created a red box object `GameObject highlighter` and a `GameObject to_highlight` that points to the object it should highlight.
    - Multiple selection allowed for multiple highlighting targets.
    - The same amount of red frame objects are generated as the number of slides.
- It's time to refactor because it smells fishy.

- Create `public class Slide`.
- Decided not to inherit MonoBehaviour
    - I don't know if it's the right answer.
- This generates two GameObjects: the slide itself and a red frame GameObject for highlighting
- Add "Slide" tag to GameObject
- The update vector of the physics operation is a member of Slide.
- The hit target of the raycast comes from a GameObject, but in this design, I want to get a Slide object from that GameObject.
    - I'm sure there is some better design...
    - I made something like this and AddComponent.
cs

```cs
public class GetSlide : MonoBehaviour
{
    public Slide slide;
}
```

    - There was no option to AddComponent to the Slide itself.
        - AddComponent takes type arguments to instantiate

- All errors in MakeSlide.cs, which was managing the slides, have been resolved.
- Check for errors in LaserPointer.cs
    - The problem is the `Dictionary<GameObject, bool> is_selected = null;` that was created in a rush job when multiple selections were implemented.
    - This should be absorbed well in this refactoring rather than a minor fix.
    - So, first comment out the entire multiple selection-related process and pass the compilation through.
- Runtime error: NullPointerException when calling highlighter thinking it exists as a single object
    - Members for single objects that are no longer used should be removed.
    - Compilation errors make it clear what needs to be fixed.
- If you simply replace the traditional single-selection code with `obj.GetComponent<GetSlide>().slide.highlited = true;`
    - But it is strange that the internal structure of such a slide is exposed on the laser pointer side, so we prepare a method for single selection and call it.
- Comment out the code that changes the highlight color once

- It took some time to scale the highlight red frame, etc., but the single selection works as it should.
- Multiple selections should be thought about carefully, not just following the changes in this object integration.
- This is happening because "multiple selection" was added after the fact where there is only "single selection" in the selection state.
cs

```cs
GameObject selected;
Dictionary<GameObject, bool> is_selected = null;
```

- Single-selection when selected is not null, multiple-selection when is_selected is not null, and so on.
- I tried uncommenting it to see what kind of compile error I was getting, but it was just a difference between Slide and GameObject, so it was an easy fix.
- Unexpectedly, it moves easily.
- No highlighting when multiple selections are made (from the original)
    - I did `is_selected[y] = true;` where `s.highlited = true;` and it worked easily.
    - Fixed undo when deselecting, etc.
    - Since only selected items are moved by checking is_selected when moving, it might be better to change this so that only highlighted items are moved, so that the appearance and the behavior match.
        - I removed is_selected and it is working fine.

- Change highlight color
    - Previously, there was only a single selection, so you could only change the material of a single object
    - Change colors when multiple selections are made?
        - Should materials be common?
    - I checked and it only changes color if the laser pointer is brought closer than a certain distance to the teleport portal when a single selection is made in the first place.
    - I added a method to change the highlight color when a single selection is made, but I'm afraid that in the future I'll call this when multiple selections are made and say, "The color won't change...

- Drag behavior for single selection is absolute position shift.
    - Multiple choice is converted by quaternion since the implementation is newer.
    - Common behavior, multiple selection highlighting at all times, fallback to single selection mode if only one is selected in multiple selection mode
    - Is it safe in terms of speed with constant highlighting?
        - 57 FPS without physics, 37 during the occurrence, and about 48 after the end.
        - About 38 after constant highlighting.
        - I don't know how it would be on a real device since I'm talking on the Unity Editor... well, it doesn't seem to be an immediate no-no in terms of the reduction ratio.

    - Ultimately, the difference between these two lines
    - single `selected.transform.position = ray.origin + ray.direction * distance;`
    - multiple `x.transform.position = diff * (start_positions[x.gameObject] - eye) + eye;`
        - `Quaternion diff = Quaternion.FromToRotation(start_direction, ray.direction);`
    - Oh, there was still a Dictionary with GameObject as the key.
        - `Dictionary<GameObject, Vector3> start_positions = new Dictionary<GameObject, Vector3>();`
    - Let's give the Slide object a member named drag_start_position.
        - Create startDragging and endDragging, and also "turn off physics on multiple drags as well as single drags" which was pending.

- Well, sometimes it doesn't work that easily.
    - Atmospherically, there seems to be some kind of malfunction in the physics.
    - Collider is disabled in unselected state for some reason.
    - I'll comment out the parts that seem DISABLE.
    - When I comment out the startDragging, Collider is no longer disabled, but it goes one step further and still stops.
    - Ah, I see. When multiple selections are determined, the drag starts as soon as the target is highlighted because the search for the target was initially started with the mouse down, but now the bug is that the drag starts even though the mouse is not down because the target is highlighted all the time.

- getSlide is called with null argument at the start of a single drag
    - Hmmm, this seems to be a time sensitive issue that would be resolved faster if I don't try to solve it today. Let's make it a task for next time.

---
This page is auto-translated from [/nishio/リファクタリング20180726](https://scrapbox.io/nishio/リファクタリング20180726) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.