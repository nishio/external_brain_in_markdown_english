---
title: "Automatic path grouping"
---

2020-02-10 [[pRegroup-done-2020]]
- Grouping of paths?
    - > I'm not happy about anything because only one path is moved, such as an arrow that seems to consist of multiple paths.
    - The path down should be implicitly grouped.
        - [[Groups with no nameplate]] is required -> Done
- When flushing the path buffer, add groups with paths as children instead of adding paths individually
- The path buffer flushes were running on both the click of the path button and leaving the path mode, which would draw the same thing twice.
- The leave-from-pass process also runs when the pass button is pressed while in paz mode.
    - Whether the behavior is appropriate...
    - But it's weird that it flashes when I click the pass button to enter paz mode.
    - Deleted bus pattens side.
    - →Done
---

Grouping of paths?
- Is it really necessary to be able to "drag a path around?"
    - Only one path, such as an arrow that seems to consist of multiple paths, is moved and nothing makes me happy.
- Would we need "paths grouped together?"
    - But the group needs a nameplate.
    - Are you sure the nameplate is just text?
    - Shouldn't the compressed version of the selected path be the default?
    - Compression occurs by daring to text.
        - Simply making a reduced image is not enough.
2019/07→2019/12
- Forcing groupings to have a nameplate is not a good idea.
- Dare to text" → Idea of imposing restrictions on users
- Wouldn't it be nice to have an implicit group at the point of "lasso selection and dragging" in the first place?
    - → I'm having a hard time deciding what kind of UI would be best.
        - When clicked, an implicit group that wraps the entire path is displayed.
        - Ungroup" in the balloon menu
- (pending)

relevance
    - [[Pen input on stickies]]

---
This page is auto-translated from [/nishio/パスの自動グループ化](https://scrapbox.io/nishio/パスの自動グループ化) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.