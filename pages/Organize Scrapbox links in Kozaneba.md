---
title: "Organize Scrapbox links in Kozaneba"
---

The feature that heavy Scrapbox users (me) have been wanting is now a reality.
If you paste a Scrapbox URL into Kozaneba, a Scrapbox kozane is created, and if you press the expand menu of the kozane, all pages within 2hops become kozanes, and you can move them freely.

Scrapbox is a very complicated system, and when there is a page that repeatedly refers to something, the number of links to that page gradually increases, and the system becomes somewhat incomprehensible.
I prefer to divide them into several groups, but it is difficult to do so on Scrapbox because I can't move the card view of links.

This Scrapbox page on the "KJ method" has 97 "pages mentioning the KJ method. As I keep mentioning the KJ method, the number of pages gradually increased and it became like this. I want to organize them.
![image](https://gyazo.com/eed4b8e9ad08d9dc99b6537b3bbb9a33/thumb/1000)

![image](https://gyazo.com/003e4464393fe4afa658ec9ca544ccc9/thumb/1000)
![image](https://gyazo.com/95a6a78875eb880d322c687e4cca03c6/thumb/1000)
![image](https://gyazo.com/aa2044dcbd24d0a33313a72479e65c51/thumb/1000)
![image](https://gyazo.com/3ba0aafedbc70c3040f790981dee5ed8/thumb/1000)
![image](https://gyazo.com/566102e96a749bde34116f48fb2290f6/thumb/1000)

I want to copy the title of a Scrapbox kozane, etc. with copy text. If I can copy it, I can paste it as it is and make a normal kozane.

![image](https://gyazo.com/d43a218fff7b637e7edb47c5fb848774/thumb/1000)
![image](https://gyazo.com/a5fc4d0e1978332aa8d6fd49fd18a4f9/thumb/1000)

I would like a menu that expands the selected group to fill the screen.

When you want to move a selection more than one screen, if you scroll with a two-finger gesture while the selection is still selected, the selection will not scroll.
It should work fine, even if you zoom out while selected.

It's going to reproduce when you click on a group that is empty as a means of reproducing the mysterious displacement.

I'm taking screencaps of each group because I have no idea what the whole picture looks like in the image.
![image](https://gyazo.com/2eaee5f71965a88fb8e62aef604b1fee/thumb/1000)

Oh, well, let's just do the lead-only sharing for now.
[https://kozaneba.netlify.app/#view=mysoGOrUgjEKXjZY4obK](https://kozaneba.netlify.app/#view=mysoGOrUgjEKXjZY4obK)

It's not a good idea to categorize, but if the clutter is at a level where it's impossible without categorization, I think it's better to first categorize it and then divide it into smaller spaces and then work on them individually.

Hmmm, I'd like to follow Scrapbox one more step, but the two-hop link loading would be massive, including existing ones.
Would it be nice to have the ability to add only those pages that are not already there?

![image](https://gyazo.com/b090bbf68af84fdc4acbeebcccc83529/thumb/1000)
I opened the "Nodes of Thought" series with a casual mind because I didn't know where to put it by just looking at the title, but it is called "Nodes of Thought" because "at the time I wrote it, I was connected to various concepts and couldn't separate them and couldn't come up with an appropriate title". I was in trouble when I did.

Well, I'm making progress because I've become "well, it's the vector and dimensional side of the story" rather than just "the nodal point of thought" in terms of getting a place to put things in place.
It's 26:00 and I'm afraid to make a backup and go to bed because I'm afraid I'll sleepwalk and break it by operating it in a weird way.

Scrapbox does not assist in creating a hierarchical structure
Scrapbox can move lines within a page in 1.5 dimensions using bullet points, but the page, which is a bundle of those lines, looks like a card but cannot be moved freely.

There is no need to organize them all at once, because they have accumulated over the years, and if we assume that an average of 10 kozane can be produced from a single page, that's a pretty big 1000-sheet class.

After tomorrow, rather than continuing to organize, our priority should be to fix the things that bothered us after using the system this time.

The good thing about Scrapbox is that you can easily browse pages that have been written over the years and contain certain keywords that have been manually added by humans; the bad thing is that it becomes impossible to list them when there are 97 of them.
The good thing about Kozaneba compared to paper stickies is that it can handle Scrapbox's digital data as it is

Making 1,000 paper sticky notes is daunting. It would be stupid to use text when there are digital images, and if you print the images, you would have to do a lot of chopping and tapping on the paper. If you want to stick to physical sticky notes, sticky note printers and the like are the limits of current technology, but there is no need to stick to physics. Digital stickies are better.

Digital Kozane does not occupy physical space even if hundreds of sheets are spread out. It does not need to be put away and can be kept for months without fading. Digital kozanes are searchable, although we have not yet implemented this feature in Kozaneba, and they can be duplicated and made larger if you think it is important. It can be duplicated and enlarged if you feel it is important. You can have links to more detailed information.

Minor points of concern
- Image highlighting is strange when selecting a range
    - Is there something wrong with the bounding box?
    - Is the color wrong too?
- Range selection, heavy?
    - Heavy bounding box calculations?
    - Heavy React updates?
- Two-finger scrolling, heavy?
    - Is this another heavy React update?

---
This page is auto-translated from [/nishio/KozanebaでScrapboxのリンクを整理](https://scrapbox.io/nishio/KozanebaでScrapboxのリンクを整理) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.