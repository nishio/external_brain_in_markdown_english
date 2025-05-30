---
title: "Kozaneba Development Diary 2021-09-12"
---

from [[pKozaneba]]


I want to use the large kozane in the upper left corner as the title.
- ![image](https://gyazo.com/201b1ef86921dba92c7d47d9c8fcd376/thumb/1000)
    - ![image](https://gyazo.com/bd0acfe46820849e56d77d4df27440aa/thumb/1000)
    - When adding a group title in this state, it is time-consuming to select and delete items other than those needed.
    - Put a button to select only the largest kozane?
        - In that case, should the scale of the created group also be adjusted to that kozane?

AddKozane It would be nice to be able to adjust the fontsize


![image](https://gyazo.com/54241c98f65a3774ffc23234c857afac/thumb/1000)
- I tried and saw that the braces are not there yet, but the arrows are fine, but I got the feeling that they are not.
- I guess that's what happens when you "draw an arrow from the center of gravity"...
- I expected this to happen. To do this, I need to do "select 2 and add arrows" 4 times, that's a bit of a hassle. I could add a menu to do this sort of thing, but what is the name of this operation...
    - ![image](https://gyazo.com/9edeef836dc4663a9d821a1fc48fe13e/thumb/1000)
- What I have in my brain is a "two-part graph".
    - [2-part graph - Wikipedia](https://ja.wikipedia.org/wiki/2部グラフ)
- ![image](https://gyazo.com/db24cc8fbda75c98c436458fb4fcf5fc/thumb/1000)


- [[🤔Arrow additional UI]]
> [VoQn](https://twitter.com/VoQn/status/1436737605840764932): It's just a quick idea, but I was thinking that if we could make it like a node editor, where you drag from the terminal UI to each task to connect them, the number of operations could be reduced to one at a time. I'm not sure if it's a good idea or not.
- ![image](https://gyazo.com/26620e7c9196d42fa70d54753a009e15/thumb/1000)
> [nishio](https://twitter.com/nishio/status/1436744219742203911): I think it's possible to have the terminals out if the main purpose of the tool is to connect with arrows, but I think it's annoying to have them out all the time with tools that don't. I don't like the fact that "switch to arrow mode" also introduces a mode...
> [VoQn](https://twitter.com/VoQn/status/1436751102075043840): the main tool is just to dump ideas in your head, right?
> I thought if I did it this way, it wouldn't be so gross.
- ![image](https://gyazo.com/2950335587921f1b48dc4725ac4ab149/thumb/1000)
- ![image](https://gyazo.com/1dc94c5352d0670f86d0de7627111609/thumb/1000)
> [nishio](https://twitter.com/nishio/status/1436752076948664321): I see.
> What do you imagine would happen in these situations?
- ![image](https://gyazo.com/6c40f1d9e3a5a8c771aa6e8310ad9457/thumb/1000)
> [VoQn](https://twitter.com/VoQn/status/1436753138506088454): is this better to assume that the position of the coordinates of each idea is also the will of the user?
> (Is there a concern that the software might have a bias if it sorts and aligns itself?)
> [nishio](https://twitter.com/nishio/status/1436753583379083264): I think the main value is that you can freely position the coordinates of each idea. So, I have an image that arbitrary sorting and alignment is about "no, absolutely not".
> [VoQn](https://twitter.com/VoQn/status/1436755213898059780): right - (I kind of felt that way)
It is not so difficult in the case of a >1→N graph or an N→1 graph, but it seems that it is not so easy to draw a graph that connects arbitrary coordinate spaces.
> I'll give it a bit of a go.
> [VoQn](https://twitter.com/VoQn/status/1436765275769032704): It's not the main feature, but it's not worth the effort in terms of how it's implemented or the visuals that are implemented. ... (This is what I can come up with right now.)
![image](https://gyazo.com/63d0f11136f978303d85e65a98d9e80c/thumb/1000)
![image](https://gyazo.com/efc63108e90f03b3da0108f44251c1e3/thumb/1000)
> [nishio](https://twitter.com/nishio/status/1436766830362693632): I'll hold off because the arrow function was only added last week, and I don't know how many cases there are where you would want to draw arrows, but if you want to draw a lot of arrows, this might be better than " I'll hold off on that for now, but if I want to draw a lot of arrows, this might be better than "select and then menu".
> It's like adding a layer that corresponds to the enclosure of the selection for the arrow...
> [nishio](https://twitter.com/nishio/status/1436767233376612355): (In terms of priorities, the lack of arrow delete functionality is serious, so I'll put that on first, and then the range selection implementation will be comfortable because of React's state update. Then, after solving the problem of not being able to select...)

Ah, with the current implementation, the range selection is rectangular, so if you want to draw an arrow from B to A, you'll have to move A to a position where it can be selected along with B. That's subtle...

![image](https://gyazo.com/00bba1c295614aa54a083f50c3e15972/thumb/1000)

next  [[Kozaneba Development Diary 2021-09-17]]

---
This page is auto-translated from [/nishio/Kozaneba開発日記2021-09-12](https://scrapbox.io/nishio/Kozaneba開発日記2021-09-12) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.