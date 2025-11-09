---
title: 'The "box metaphor" and "tag metaphor" of "assignment."'
---

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/> Explanation of "[[Box Metaphor]]" in "[[Assignment]]" and its inconvenience and "[[Tag Metaphor]]".
<img src='https://scrapbox.io/api/pages/nishio-en/GPT5/icon' alt='GPT5.icon' height="19.5"/>
Two metaphors for "assignment

## 1) Box metaphor
.
- Variables = "boxes" for contents
- Assignment = copying a value into a box
- Open the box and read the contents (value) each time you refer to it.

- Situations that can be explained well
    - A sense in which a primitive value is placed on the stack, such as `int x=3;` in C
    - Explanation of value semantics (copy) assumptions

Inconvenient and misleading points
1. overlooking sharing (aliasing)
- It is easy to misunderstand "copy the whole box" in a language that shares objects and arrays.
python

```
a = [1,2]; b = a # Reference to the same list in b
b.append(3)
# In the box metaphor, it's supposed to be "another box" but in fact a changes too -> confusion
```


2. misunderstanding of argument passing
Invites the "pass-by-value vs. pass-by-reference" debate: Python/JS is "pass by-reference to an object" = touches the same object as the caller, but a box can easily look like "pass-by-copy".
3. confusion between reassignment and modification
    - Reassignment: variable changes to point to a different object
    - Change: Change the internal state of the same object
With a box, it is easy to mix up the two.

2) Tag/Label metaphor
- The object (value entity) exists first, and the variable is a "tag" that is attached to the object.
- Assignment = Change to which object a certain tag name is pasted (bound).
- Multiple tags can be placed on the same subject (alias = alias)
- Change is "change of subject" and reassignment is "re-pasting of tags"

advantage
- Alias references and identifications can be explained naturally
python

```
x = [1,2]
y = x # I put a new tag y on the same object
y.append(3) # The object itself is modified, so it changes from x's point of view
x is y # True (same object)
```


- The identity of the reassignment is clear.
python

```
y = [9] # Replace the tag of y with another target. The original target is retained by x
```


- Clear distinction between immutable and mutable.
    - Immutable (number, string, tuple, etc.): The content of the object does not change. Change is always "create a new object and replace the tag."
    - Mutable (arrays, dictionaries, etc.): can change the target on the fly
- GC's intuition: if no tag is attached to any object, it is subject to collection.

Which language is best suited for
- Compatibility with Python / JavaScript / Ruby / Java (reference types) and other reference semantics-centric explanations
- Box intuition still useful for C primitives (used together as needed)

Sorting out common confusions (rephrased in tags)
- function argument
A new temporary argument tag pasted on the target exists only during the call.
If the target is changed, the caller is also reflected. Even if a temporary argument is replaced with a different target, the caller's tag remains unchanged.
python

```
def f(v):
    v.append(0) # change target -> reflect in share
    v = [9] # v's tag re-paste -> irrelevant for the calling tag
L = [1]; f(L)     # L -> [1,0]
```


- Shallow copy / deep copy
In the tag metaphor, shallow copying is "only the outer object is new, while the inner object is reused tags to the same object as the original". Deep copying is "creating and pasting a new object on the inside as well.
python

```
import copy
a = [[1],[2]]
b = copy.copy(a) # shallow
c = copy.deepcopy(a)
```


- Distinguish between reassignment and mutation (very important)
javascript

```javascript
let a = {n:1};
let b = a; // b tag on the same object
a = {n:2}; // a tag is pasted to another object (b is not affected)
b.n = 3; // change the "original object" that b points to (independent of a)
```


Guideline for use (abbreviated version)
- Box meta: useful for explaining primitives with value copying assumptions and basic types in C
- Tag Meta: appropriate for explaining objects/references, variability, aliases, GC in modern languages (less misunderstanding)

one-line summary
- Box = "value in a variable"
- Tag = "Variable is "to which subject is the name tag attached."
If the reference, variable, and argument behavior is correctly intuited, the tag metaphor is safe.



---
This page is auto-translated from [/nishio/「代入」の「箱のメタファー」と「タグのメタファー」](https://scrapbox.io/nishio/「代入」の「箱のメタファー」と「タグのメタファー」) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.