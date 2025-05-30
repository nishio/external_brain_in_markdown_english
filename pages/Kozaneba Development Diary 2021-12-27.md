---
title: "Kozaneba Development Diary 2021-12-27"
---

> When the position of a kozane in a nested group is updated, some value of the parent's parent group is not updated.
![image](https://gyazo.com/60bda293dd176921a1b8f55e5c319687/thumb/1000)
![image](https://gyazo.com/37d508ab6716938b080bdc143c73ac49/thumb/1000)
The parent's POSITION is updated, but its parent's is not.
On a related note, "If you take the G1 out, put it back in, then take the 1 out again, it jumps."

fixed
- ![image](https://gyazo.com/f9eb20eaf29055042ea763b46cb17334/thumb/1000)

---
> "If you take the G1 out, put it back in, then take the 1 out again, it jumps."
without X
`do_drag("1", "ba", 100, 100);`
![image](https://gyazo.com/7334ea3c47bb87e164032aa9ca29c327/thumb/1000)

with X
js

```javascript
do_drag("G1", "ba", 0, 0);
do_drag("G1", "G2", 0, 0);
do_drag("1", "ba", 100, 100);
```

![image](https://gyazo.com/938d31d1c3aeea7b078f5615b33f9dfd/thumb/1000)

:
|  | A: 1 | *left,top | G1 |  G2 | delta | B: 1 | CSS:left,top | *left,top |
| -- | -- | -- | -- | -- | -- | -- | -- | -- |
| without X | 0, 0 | 184, 199 | 0, 0 | 0, 0 | -84, -99 | -84, -99 | -150,-150 | 100,100 |
| with X | 0, 0 | 225, 225 | 0, 0 | 41, 26 | -125, -125 | -125, -125 | -191,-176 | 59, 74 |
- A: before drag
- B: after drag
- *: getBoundingClientRect

:
|  | A: 1 | *left,top | G1 |  G2 | delta | B: 1 | G1 | G2 | CSS:left,top | *left,top |
| -- | -- | -- | -- | -- | -- | -- | -- | -- | -- | -- |
| without X | 0, 0 | 184, 199 | 0,0 | 0, 0 | -84, -99 | -84, -99 | 0,0 | 0,0 | -150,-150 | 100,100 |
| with X | 0, 0 | 225, 225 | 0,0 | 41, 26 | -125, -125 | -125, -125 | 0,0 | 41, 26 | -191,-176 | 59, 74 |
| drag G2 | 0,0 | 180, 230 | 0,0 | -4,31 | -80, -130 | -80, -130 | 0,0 | -4, 31 | -150,-150 | 104,69 |

Simpler problem reproduction procedure
- When you v-drag G2 in a nested group and then move 1 out of the way, it is -v off from the expected position.

This seems like an over-correction, but why did you correct it in the first place?
Are there cases where corrections should be made?

You're only adding the POSITION of the direct parent, which is bad.

done

release notes
- Fixed a bug that caused the endpoints of arrows to groups to be incorrect when two or more groups were nested
- Fixed a bug that caused items to move to a different position from the drop position when drag-dropping items from two or more nested groups.

2021-12-28
release notes
- Increased the degree of line transparency
- Fixed a behavior that caused unintentional range selection when the mouse was down on a line while trying to drag a kozane.
    - Lines no longer receive mouse events.

I'm having trouble figuring out how to edit against the arrows.
What I'm feeling after using it.
- I want to Undo when I accidentally put an arrow in the wrong direction.
    - You can delete it.
    - I'm cloning and deleting Kozane now.
- The only way to do that is to draw a line through three items and then re-create the whole thing when you think the fourth item was correct.

For these two, you can choose and "get out of line" action.
- If there is more than one line, it will be missing from all of them, but...

---
This page is auto-translated from [/nishio/Kozaneba開発日記2021-12-27](https://scrapbox.io/nishio/Kozaneba開発日記2021-12-27) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.