---
title: "Kozaneba Development Diary 2021-09-06"
---

from  [[Kozaneba Development Diary 2021-09-03]]

![image](https://gyazo.com/3b1885028ba43611aedaae93f8879a39/thumb/1000)

---
Write down what you will do when you wake up
- Add frontmost SVG layer
- Create an arrow object for now.
    - N ko
- Try drawing and see if it corresponds to dragging items
- Add a click handler
    - Delete first
- Switching arrow heads

- Paste now, always reassigning IDs, but only when duplicating.
- Create a script to view file dependencies and generate JSON
- Put it on Kozaneba.

-----
Create an arrow layer today.

First, place the SVG element
- ![image](https://gyazo.com/fe3d5b0065c375c28e68e84b1ead71e0/thumb/1000)

Next, make arrows, start pomodoro
- Pomodoro end
- ![image](https://gyazo.com/d5f5b0cd7668bc0759fc5d4ddd493246/thumb/1000)
- Lines are now drawn according to the item's position, but the intersections with the edges are still being calculated.

Next, we'll complete the intersection calculations to give it an arrow-like appearance.
- Pomodoro start
- ![image](https://gyazo.com/8f5f5679a2472d6acd231c7c7fa3cc8e/thumb/1000)

✅Add foremost SVG layer
✅Draw arrows for now.

The next step is to change the arrows, which are now hard-coded, to a form made from data.
- = Create an arrow object
- Pomodoro start
- done

Next time, let's put the test code into a more complex situation and see if it displays as expected.
- Pomodoro start
- done
- ![image](https://gyazo.com/60e1e72b13f43455c9bd800beb22fea3/thumb/1000)
- ![image](https://gyazo.com/747d83d8fddf31626f07b8d61a36239f/thumb/1000)

Paste now, always reassigning IDs, but only when duplicating.
- First try to import arrows in small JSON
- Allow the arrow to be copied in the first place.

Implement copy before paste
- What if a partial selection is made?
- For example, if you select and copy only 2 vertices of an arrow that consists of 3 vertices, it should be an arrow if it consists of 2 vertices.
- What if an element is deleted in relation to
    - It is subtle to notice the timing of the drawing.
    - Annotation update process should be run after the item is deleted.
    - What about REPLACE?
        - Should the ID be maintained?
- Selective copying does not involve updating the state because it is, after all, a "copy.
- Since it is not a tree, the process of reassigning IDs must be handled separately.

I found the implementation of copying before pasting to be quite a pain in the ass.
- Possibility of partial selection by the user
- Well, we're starting to see a lot of it, so let's implement it.
- Pomodoro start
- I could copy-paste.
    - However, bugs were also found.

1Repair Pomodoro and build a Python library in the remaining time.
- > Make a script to look at file dependencies and generate JSON
- I found one more bug along the way, so the library didn't get going.

> Make a script to look at file dependencies and generate JSON
- > Post it on Kozaneba
- Implemented (but not practical)
    - Kozane, because I generated all of them to 0,0.
    - ![image](https://gyazo.com/26cc13d9e4fbd41021fb2a3c156f95ad/thumb/1000)

I'd be tempted to add physics...
- ![image](https://gyazo.com/3b1885028ba43611aedaae93f8879a39/thumb/1000)

---
> [nishio](https://twitter.com/nishio/status/1434833231510061063): I'm tempted to add physics to Kozaneba, but I don't think it's a good idea to mechanically apply physics to a place where the physical arrangement is an intellectual product. I don't know...

> [nishio](https://twitter.com/nishio/status/1434833819920519173): I don't know if it's a matter of turning on the physics, or if it's a matter of maintaining the proximity of objects that were in close proximity at the time the physics was turned on as "a relationship expressed by a human being through proximity". Is it better to make the physics calculation in such a way that the proximity relationship is maintained?

> [nishio](https://twitter.com/nishio/status/1434834277535866883): But when you put it that way, "placed a bit apart" is also a statement of "related, but not enough to stick right next to it". ...

> [nishio](https://twitter.com/nishio/status/1434834460319485959): the further apart you are, the less relationship you have and the less need you have to maintain it.

> [pokarim](https://twitter.com/pokarim/status/1434835595457544194): It's just a thought and I'd recommend going through it, but (sorry), if the distance is a certain distance, the closer the closer the attraction and the farther the farther the repulsion, the more cohesion between the closer ones, I wonder if it would be possible to do something like that. Maybe there should be some kind of frictional force. I don't know if such a thing would be a match for intellectual production systems, but I'd be interested in either result.

> [nishio](https://twitter.com/nishio/status/1434865675525185541): If we use "far away and repulsion in proportion to it", it will scatter like a big bang, so we need "the further away it goes, the closer it gets to zero", and "nearness and attraction". If implemented naively, it will collapse into a single point, so for intellectual production, we need "a repulsion that doesn't dip any closer than a certain point". The area in between has room for ingenuity.

> [nishio](https://twitter.com/nishio/status/1434866417430454272): For example, if you move a pinecone closer than one, it will attract it, and if you move it further away than two, it will try to move further away. It is like oil drops in water. However, when there are long thin clusters, they will repel each other through the points in the cluster that are farther apart and break up into round clusters (also like oil droplets).

> [pokarim](https://twitter.com/pokarim/status/1434866637404966915): Yes, that is true. I think it would be interesting if it were adjusted well. It would be ideal if we could prepare a logic to make the adjustment in a way that is not too deliberate and "results in something like that.

> [nishio](https://twitter.com/nishio/status/1434868937234141184): If you generate a strong "force to keep the current distance" (like a sticky rice cake in physics) at the very edge of the penetration, it is hard to shred even if there is a repulsive force Maybe...

> [pokarim](https://twitter.com/pokarim/status/1434870256774774787): I see, rice cakes. It seems to me that the difference between a rice cake and a mochi varies greatly depending on whether they are just close together and not sticking to each other or exactly sticking to each other. I feel that the centers are attracted to each other and the contours of the kozane are repelled by each other, and that if we adjust the relationship between the distance and the force, we can prevent the rice cakes from sticking, but I'll have to try a little more to find out.

> [nishio](https://twitter.com/nishio/status/1434878806200750083): I was thinking about it and wanted to do it w
- ![image](https://gyazo.com/329fb606d91e2d8648243db600dd303d/thumb/1000)

> [nishio](https://twitter.com/nishio/status/1434913371871014926): I've added physics, but it's not very interesting as it stands pic.twitter.com/sWkyj00bh1
- ![image](https://gyazo.com/de6730a0979920791d3cb494ffdb672d/thumb/1000)

> [nishio](https://twitter.com/nishio/status/1434913718219931653): there is a way to remove the vertices where the arrows are clustered together, or to represent the directory hierarchy as a group

> [nishio](https://twitter.com/nishio/status/1434914603465465864): Oh, I thought AdaDelta didn't work as expected, but it's mean square when it should be root mean square!

> [nishio](https://twitter.com/nishio/status/1434916103826722819): Also, it would be nice if anything the user drags from the initial position is pinned and stuck.

> [nishio](https://twitter.com/nishio/status/1434929099684728834): I thought it would be a little too much to do physics with JS, but when I took a profile, I found that the reason it was slow was because I didn't add a key to the SVG line in the React rendering. It was because I didn't add a key to the SVG line in the React rendering.

> [nishio](https://twitter.com/nishio/status/1434935229811073025): there are 666 import relations between 197 files and if you visualize them as they are... they are not visualized! Uni!
> gyazo.com/5723029877bfb6…

> [nishio](https://twitter.com/nishio/status/1434936220400816129): I wonder if the problem is that there are 2000 line elements in the SVG, because it is taking a long time even when ungrouping, which is a problem before physics.

> [nishio](https://twitter.com/nishio/status/1434944644232593409): The physics step itself is about 200ms, so the drawing is simply too heavy.
> Well, this application is not the main purpose, so let's interpret it as a kind of load test.
> In terms of visualization of source code, directories can be represented as groups, and only references that cross over them can have arrows drawn.

> [nishio](https://twitter.com/nishio/status/1434950122299740161): tomorrow we'll have a meeting, edit the video, rework the screenshots, and continue with the source code visualization when we have more time!

> [nishio](https://twitter.com/nishio/status/1435050971588009991): I wonder if it is possible to rewrite 4000 SVG line elements 10 times per second in a modern browser to begin with.

---
This page is auto-translated from [/nishio/Kozaneba開発日記2021-09-06](https://scrapbox.io/nishio/Kozaneba開発日記2021-09-06) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.