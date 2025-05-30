---
title: "Kozaneba Development Diary 2021-08-27"
---

prev  [[Kozaneba Development Diary 2021-08-26]]

I think it would be easier to introduce an arrow layer in the forefront.
Braces are good for object layers.
- Better not to split into separate objects.
    - Custom Styles.

Relationships between multiple boxes
- It can be easily drawn once the location of the box is determined.
What if you can draw an arrow against an arrow?
- Circular references can occur.

Groups are also "relationships among multiple boxes" in
- The bounding box of the child element is calculated first to determine its own position.

I was thinking about the arrows, but it's not too difficult if you completely make the arrows a layer to be written afterwards.
in that case
- You can't put a kozane on top of an arrow because the arrow is always the frontmost surface.
- Arrows cannot be drawn against arrows because arrows are a different kind of object from "boxes" such as kozane and groups
become

- [[Dangling is not grouping.]]
- Perhaps I'm unconsciously choosing the left way because I'm using the Kozane method from the state of paper stickies with no "grouping function" etc.
- On the other hand, as a new feature, "Now you can group stickies in a way that paper stickies couldn't!" will appeal to people who started using it after seeing it, so they will unconsciously choose the right way to do it.
- You can "make it bigger," which was not available on paper stickies!
- You can use a large space inexhaustibly and arrange them in a way that was difficult with paper stickies!

---
![image](https://gyazo.com/872f3897132974239c3ad539a6a8df69/thumb/1000)
- Hmmm, this looks like it could be put back together.
- But if you give the link to someone else, and then put it back into a mode where people who know the link can edit it, of course they can.
- Is that okay with you?

Google Spreadsheet
- ![image](https://gyazo.com/329041b89912f417de2e5ddc1de21cff/thumb/1000)
- ![image](https://gyazo.com/5aadc03eb256d471606454a1f1488b34/thumb/1000)
- ![image](https://gyazo.com/492cf77957839cad1f61d9c9b36b56a4/thumb/1000)
- The link for view is the same as the link for edit.
- The screen I opened at the time of the view is still in readonly, but when I reopen it, I can write on it.

Hmmm, so it's the same shape I was trying to create, is that right?
- I thought it would be better to have separate view and write links and be able to turn them on and off separately, but I guess it works fine in most cases without such a feature.

Cases where the current design causes problems
- After publishing a link to a view, there is no way to add a writer if you want to.
    - Reverting back to EDIT could result in unexpected people being promoted to WRITER.
        - This is because the specification says that "the person who edits is promoted to writer and has write permission even after being returned to view.
    - In the first place, it is unlikely that you will need to add a WRITER since it is basically intended for personal use.
    - I'd like to have "receive the UID and add it" or "issue a separate invite link to add it to writer while in view mode".
        - Just the latter.

![image](https://gyazo.com/632a00c807872d619df58dbddc3164ab/thumb/1000)
![image](https://gyazo.com/aa259e8b528230a5a37dc1c60b9b85bd/thumb/1000)

Lead-only sharing is now available! You can share Kozaneba Kanban directly instead of images!
- [https://kozaneba.netlify.app/#view=23YyYfzS1dTx05tugVW7](https://kozaneba.netlify.app/#view=23YyYfzS1dTx05tugVW7)
- There is still no function to show the image when it is posted to Twitter or other sites.
- ![image](https://gyazo.com/8b4d5297c5a6632c22596fe5b0a2dc57/thumb/1000)

- With create and delete copies, if you accidentally share something you shouldn't show, you can just copy it and delete the original one. Oh, you didn't create an error process for when something you tried to open is not there.
- Oh, and I haven't finished supporting touch events yet, so anyone who opens the link on a smartphone can't do anything.
    - In the future, I would like to see a flow of "add handwritten kozane", "handwrite in the opened dialog", and "become Gyazo kozane".

To the front of the group when opened
Even when 4 cards are added, the small group margin makes it difficult to select them.
GyazoGIF Kozane

There is no flow line for people who have received the lead-only share to go to the home page to view the tutorial.
- If you click on the name of the service, you will be taken to the top page or
So when I open a read-only share on my other device, I can't edit it because I'm not logged in, but I can't log in because it's not editable and I don't get the cloud save menu either.

I use the split menu a lot, but I almost always Replace.
- If it is possible to clone a clicked Kozane, there is no need to use "Add" and "Replace".
    - split, add = clone, edit
    - split, replace = edit

Huh? I see, the reason I had trouble using images from Gyazo in Regroup was because it was in Canvas, and if I simply paste it as an img, there's no problem?
- If you want to make Scrapbox Kozane, you need Gyazo loading function after all
- The DOM is different in this area, and I think it's making the problem too difficult to do with user extensions.

ts

```typescript
export const id_to_dom = (id: string, offset: TOffset) => {
  const item = get_item(getGlobal(), id);
  if (item.type === "kozane") {
    return <Kozane value={item} offset={offset} key={id} data-testid={id} />;
  } else if (item.type === "group") {
    return <Group value={item} offset={offset} key={id} data-testid={id} />;
  }
  return null;
};
```

It's like adding Gyazo and Scrapbox here.

![image](https://gyazo.com/437c10a3d0bc8bdfce44f8d7ef52690a/thumb/1000)
![image](https://gyazo.com/31a31d26e323a6164445e587a148ac3d/thumb/1000)
It's a choice between looking like Scrapbox (copying the CSS) and keeping it to the bare minimum of what you understand.
- Rather than making it look like a complete system, it would be better to keep it to a minimum that serves the intended function, and if users want to tweak the look, they can do so with extensions.
- In general, when you go with a perfect match to the original, it's not even a "familiar look" for people who are tweaking with UserCSS.
- I guess I'll just have to go with the minimum implementation that will serve the function...

![image](https://gyazo.com/9de8d92b2785201afdb555801d147cb2/thumb/1000)
- Maybe it's just about 2 or 3 times the size of this one...
- ![image](https://gyazo.com/8d12f6d2292a06af6804b97fddca28d7/thumb/1000)
- (of) good appearance

It looks done, but...
- Cannot drag and drop
- Cannot select a range
- Bounding box calculation is not yet implemented, so space key kills it.

- [[Manage Kozaneba development in Kozaneba]]

- [[Kozaneba Development Diary 2021-08-28]]
---
This page is auto-translated from [/nishio/Kozaneba開発日記2021-08-27](https://scrapbox.io/nishio/Kozaneba開発日記2021-08-27) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.