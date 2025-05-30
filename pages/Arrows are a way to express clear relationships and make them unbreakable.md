---
title: "Arrows are a way to express clear relationships and make them unbreakable"
---

> [nishio](https://twitter.com/nishio/status/1433356592620081155): "Putting it close" in KJ-method or other methods is a way to ambiguously express "relationships" that have not yet been clarified, while the function of drawing an arrow is a way to express relationships that have been clarified and will not disappear when "moved far away". On the other hand, the arrow-drawing function is a method of expressing a relationship that has already been clarified, so that it does not disappear even if it is "moved far away". If you just use "put it near," it will break if you move it.

> [nishio](https://twitter.com/nishio/status/1433357276169920513): grouping is a way to make the relationships expressed in "keep them close" less fragile. It can be moved as a single lump, or folded to the same size as a single kozane.

> [nishio](https://twitter.com/nishio/status/1433358725931171847): So maybe we still need an "arrow function". However, that's not what many people imagine as "something that connects two points. Something that expresses a relationship between multiple things and does not break until explicitly destroyed. A group can be considered a kind of group.

> [nishio](https://twitter.com/nishio/status/1433359690545565696): But then, it's not as if we can just increase the group implementation. The current group implementation is a tree, so it has one parent. But arrows naturally occur when one element joins multiple arrows.
> Now the group is a tree, so the enclosures do not intersect, but if the arrows are the start and end enclosures, they will intersect.

> [nishio](https://twitter.com/nishio/status/1433362642429566980): When a group is deleted, its children are also deleted. A group has children.
> Child elements constitute a group of 0/1 elements.
> Arrows and enclosures do not "possess" child elements. When it is deleted, it does not delete the child elements. It disappears when the child element is deleted and no longer has a reason to exist (if the arrow endpoint is deleted or the enclosure is empty).

> [nishio](https://twitter.com/nishio/status/1433363382942322688): yeah, that doesn't sound bad. It's not strange that they are managed separately from the ones that make up the tree, since they have different basic laws and life cycles. (At first I thought it would be a good idea to introduce separate management just for the arrows.)
> Maybe the braces are part of this.

> [nishio](https://twitter.com/nishio/status/1433365166477889539): in other words, this is what I mean
![image](https://gyazo.com/4cb105f22986d5d12a04f4bc2190b738/thumb/1000)

> [nishio](https://twitter.com/nishio/status/1433366741464141824): So I guess this is "a function that takes one or more elements and uses that information to generate decorations on the topmost layer", "no element management is required", and "elements It is not required to manage elements" and "elements may disappear". If we break it down like this, we can't have "a kozane stuck to the midpoint of an arrow" or "an arrow drawn to an arrow".
---
This page is auto-translated from [/nishio/矢印は明確な関係を表現し壊れなくする方法](https://scrapbox.io/nishio/矢印は明確な関係を表現し壊れなくする方法) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.