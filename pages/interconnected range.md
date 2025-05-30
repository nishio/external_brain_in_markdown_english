---
title: "interconnected range"
---

from  [[Assistance in dividing long sentences into stickies]]
- [[interconnected range]]
    - [[paired reception analysis]] and extract a block such that the chunk is destined for the next chunk.
- [[CaboCha]]

python

```
from cabocha.analyzer import CaboChaAnalyzer
analyzer = CaboChaAnalyzer()
tree = analyzer.parse(
    "The one I'm working on now is also characterized by "many atoms, often with multiple components depending on one atom or multiple components depending on multiple atoms, and I want to redraw only some of the components when the atom changes", so Recoil's approach seems to fit very well.")
start = 0
while start < tree.chunk_size:
    i = start
    result = [tree[i].surface]
    while True:
        if tree[i].next_link_id == i + 1:
            result.append(tree[i + 1].surface)
            i += 1
        else:
            break
    print(start, result, tree[i].next_link_id)
    start = i + 1
```

:

```
   0 ['I am'] 2
   1 ['now', 'making', 'stuff too'] 23
   4 ['many', 'atoms', 'were'] 12
   7 ['often'] 12
   8 ['multiple', 'components are'] 12
   10 ['one', 'to atom', 'dependent on or'] 15
   13 ['multiple', 'atomically', 'depends on', 'component is', 'is or is not,'] 22
   18 ['atom's', 'in change'] 22
   20 ['some', 'only components', 'I want to redraw', 'because it is a feature'] 27
   24 ['Recoil's', 'approach is'] 27
   26 ['very', 'likely to fit'] -1
```

Sharpen particles and conjugations (manual work, would like to support this mechanically as well).
:

```
me
What we're working on now
Lots and lots of atoms.
often
Multiple components
Depends on one atom
There are components that depend on multiple atoms.
Change atom
I want to redraw only some components.
The Recoil Approach
Looks like it fits very well.
```


:

```
input
I'm used to making short stickies, or shortening a long sentence, but people aren't used to it, so they put in long sentences and make "stickies that are too small to read".

expected output
me
Make a short sticky note
Chop what you've written in long sentences into shorter ones.
I'm used to it.
worldling
I'm not used to it.
I'd put it in a long sentence.
Sticky note with letters too small to read
I'll make it.

0 ['I am'] 11
1 ['short text', 'sticky note', 'make', 'thing or,'] 7
5 ['at length', 'I wrote', 'stuff'] 9
8 ['shorten', 'chop', 'to', 'I'm used to'] 22
12 ['in the world', 'people', 'because they are not used to it'] 22
15 ['long', 'as is', 'put in'] 22
18 ['The letters are', 'too small', 'unreadable', 'sticky note', 'I'll make a sticky note'] -1
```

This is a failure in the engage analysis.

[[pRegroup2020]]

---
This page is auto-translated from [/nishio/係り受け連続範囲](https://scrapbox.io/nishio/係り受け連続範囲) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.