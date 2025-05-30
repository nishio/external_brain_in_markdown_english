---
title: "Kozaneba Development Diary 2021-10-01"
---

prev  [[Kozaneba Development Diary 2021-09-28]]
(actually notes spanning several days)

Improvement of copy text
- [[Kozaneba Development Diary 2021-08-19#611dc5c7aff09e0000d00ef7]]
    - > Yesterday I implemented the copy function by selecting a range of text.
    - >  I want to improve
- [[Kozaneba Development Diary 2021-08-20#611f4dd1aff09e000057326d]]
    - > Select a range of text and copy text (2D layouts are converted to one-dimensional, and group inclusions are expressed by indentation, so they can be pasted directly into Scrapbox, etc.).
- [[Organize Scrapbox link in Kozaneba#612d1106aff09e000029b713]]
    - > ScrapboxI want to copy the title of a kozane, etc. with copy text, and if I can copy it, I can paste it as it is and make a normal kozane.
- [[Kozaneba Development Diary 2021-09-09#613a035faff09e0000ce25b5]]
    - > Copy as Text from Kozaneba does not try to keep groups indented or anything, but separately Copy as Scrapbox and Copy as Markdown.

Textualizing a Selection

- Adjacency cannot be determined by center distance.
    - Use bounding boxes.
    - Cache the bounding box calculation first?
    - ![image](https://gyazo.com/1ad01655b8195c231a475015e1ea2a28/thumb/1000)

- Which to choose when there are multiple adjacent items in the one-dimensionalization process
    - Top right to bottom left.
    - However, it does not go back to the upper right corner.
        - Not traced if either dx or dy is negative

- How to text depends on the expected output format
    - Should be put later than serialization.

input
![image](https://gyazo.com/db05909f6919219f7ea891b1a5743ad2/thumb/1000)
output(// comment)
:

```
** start cluster
* start chain
Kozaneba Development
2021/9~
** start cluster
* start chain
** start cluster
* start chain
Functions found in Regroup
Handwritten additions
Fewer people than expected had iPad+Apple Pencil
Hand-drawn "enclosures and arrows" prevent "moving items".
putting the cart before the horse
Easy to move diagram should have an "image item" since that is the item // 🤔
↔
Arrow function
Undo
Menu to Icon
** start cluster
* start chain
Required Functions
I use it and find it.
** start cluster
* start chain
Fine Features
First, try to realize it with user extensions
More samples.
Designed to be easily expandable.
Placement of expansion
I'd love to try it without reloading the browser.
import by parts
** start cluster
* start chain
Scrapbox Link Expansion
Connect the arrows
Only add pages that are not already there.
** start cluster
* start chain
Tablet Support
** start cluster
* start chain
I want to scroll the screen with a selection.
status quo
Selection display does not scroll
two-finger gesture
At least show the whole thing in spaces.
If you can do this, you can "place it at a magnification that allows you to see what's inside, use the overall zoom to place it in the proper position within the whole, and then go back to the original viewpoint".
range of selection
control
Without ReactN?
** start cluster
* start chain
Scrapbox Content Import
From BaDialog
Ignore code regions
Treat indented bullets as a group
Options for AddKozaneDialog
** start cluster
* start chain
Keichobot
** start cluster
* start chain
Hopefully Markdown can do the same.
** start cluster
* start chain
Selection textualization
Scrapbox Kozane cannot determine the appropriate wording until the default project is determined.
Texting is by title only.
Create a separate Scrapbox format export?
** start cluster
* start chain
Multilingualization of tutorials
Paste from Regroup
Additional user rendering methods
```


---
This page is auto-translated from [/nishio/Kozaneba開発日記2021-10-01](https://scrapbox.io/nishio/Kozaneba開発日記2021-10-01) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.