---
title: "Change handling of mouse events"
---

from  [[Kanban in Regroup]]
Change handling of mouse events
- Handling of mouse events, not utilizing TS types.
    - If target is null, it's not known that the process is done first, and a null check request is required.
    - Like thinking that TARGET is all kinds when it's obvious that it's a group.
    - This situation is not getting the type of support I'm getting myself.
    - Combine state and necessary variables and protect them with types
- There is a "state" and the state transitions according to "events".
    - Explicitly capture the handling of mouse events as a state transition diagram
    - I guess I'm confused because I don't have a name for the condition right now.
    - The function called depends on what tool is currently selected
    - The current mouse-related code is first divided by tool.
    - The lasso has two states, one in which it's trying to enclose a new enclosure and the other in which it's moving the enclosure.
    - I'd have to look at the code on mouse down and see if you're setting the handler there.
    - That's when you mouse down the blank.
    - This is hard to understand "what is called for at what time".
    - No. If a handler is specified, the code calls that one.
    - I have a value called drag start type for mouse down situations, but position updates on drag are generally common code.
    - They're diverging on whether it's a stylus or not.
    - They're diverging on whether it's multi-touch or not.
    - I'm doing a hit test on the mouse down position.
    - They're diverging on whether or not you're pressing shift when you don't have a hit item.
    - Groups diverge on whether it's open or not.
    - Separate processing by drag start type at the drag end
    - Ideal setting, often overlooking the details of reality.
    - Can you organize the current chaotic code?
    - The use of enum was a streak of evil.
    - But in reality, there is a common process across tools.
    - Unleash event handlers implemented in the form of tool object methods as module-scoped functions
    - But that doesn't fit the need.
    - Maybe some changes are needed in the handling of mouse events?
    - I may still need to change the handling of mouse events in this area.

[[pRegroup-done-2020]]

---
This page is auto-translated from [/nishio/マウスイベントの扱いの変更](https://scrapbox.io/nishio/マウスイベントの扱いの変更) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.