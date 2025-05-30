---
title: "What should happen when a compressed sticky is decompressed?"
---

2021-06
    - The [[Sticky note selection and compression UI design]] overlay can be interpreted as "a group that automatically closes when it loses focus.
    - It doesn't have to be a modal dialog or anything.
- Just have "open groups" and "closed groups."

Discussion for 2019-06 [[Sticky note selection and compression UI design]].

Discussion of 2019-04---.
Implementation of [Regroup
![image](https://gyazo.com/87cbfe1b54375cbe795e14ac7c4dbea8/thumb/1000)

- Relative positions of children should be preserved
    - Location has meaning.
    - There is an advantage over the paper KJ method in that this can be done.
- Child scales should probably be preserved
    - At least, they are so dense before compression that they overlap if you get them closer than that.
    - I don't think it should be spread out and scuttled.
- Absolute position of the child should not be preserved
    - If you move the parent sticky after compressing it, you will not be happy if the child sticky appears in its original position when you expand it.
    - The position of the child should be stored relative to the center of gravity, and when compressed, the parent sticky should be displayed at the center of gravity, and when expanded, it should be restored at a position relative to that center of gravity

And that's what happens when you think about the natural way to do it.
- Post-compression scuffing
- Further grouping of parent stickies = proximity
- Expand it.
When you follow the flow of the "What's the point of the stickies?
What to do?

Proposal 1: Repulsion by physics
- Demonstratively good looking, but unpredictable in behavior.
- It makes no sense for the opening and closing of one group to affect the position of surrounding stickies.
- rejection (of a manuscript, etc.)

Proposal 2: It doesn't have to be a Euclidean space.
- That's true, but I'm not sure if users will recognize it naturally.
- hold (e.g. telephone button)

Idea 3: Zoom out what doesn't fit
- ![image](https://gyazo.com/29b4f6a57c7a999567d808fef8718494/thumb/1000)
- If you zoom in, it will be the original size.
    - In doing so, C should not be larger than equal
    - As a simple View layer implementation, "If a sticky is about to overlap with another sticky, it will be shrunk and displayed to the extent that it does not overlap.
    - In this case, the relative position scale of the child is not preserved
        - (It is possible to edit the absolute position on the C side while preserving the scale, but it makes no sense.)
    - As an implementation of View, it is possible to choose "it is only the positional relationship that shrinks with shrinking, not the size of the sticky" in the first place.
        - It's not intuitive, but can you get used to it?
        - ![image](https://gyazo.com/54e280f0069a412d9dfd978cc048d1f7/thumb/1000)
        - I think it's surprisingly good.
→ Metaphor in which the entity is a point
- The question of whether the size of stickies should increase when the viewpoint is scaled up or down.
- If the metaphor is that the sticky note itself with its width is a physical entity, it is implicitly limited by "a reasonable size for a human".
- Only the central dot is an entity.
    - And it's just one point in a multidimensional space, projected onto the current screen coordinates.
        - [[Sticky note locations are multidimensional vectors]]
[[pRegroup2020]]

---
This page is auto-translated from [/nishio/圧縮付箋の展開時どうなるべきか](https://scrapbox.io/nishio/圧縮付箋の展開時どうなるべきか) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.