---
title: "I want to read all mechanical import content in Scrapbox."
---

What if you want to mechanically import content into Scrapbox and then guarantee that you have read it all

If you need to read them in order
- Example: Import and read each page of a book in order
- solution
    - 1: Create a link from each page to the next page during import.
    - 2: Start at the first page and read in order, following the links
    - 3: When you resume reading, the last page you read will come to mind if you use the LAST visited order, so you can read the page after that one.

If you do not need to read them in order
- They have 300 independent column articles.
- You want to look through the existing Scrapbox project X and post only useful articles to another project Y.
    - Cases in which X should not be imported into Y in its entirety, for example, because it contains information that should not be made public.
- I think this is important.<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
    - It's a wiki, so I can follow the links and read them in any order I want.
    - I don't want to be forced to order the content to guarantee comprehensiveness when I can read it in any order I want.
- solution
    - Tag all pages as unread on import. Example: `#unread`.
    - Create an unread page and pin it
    - A list of unread pages appears on the related page.
    - Remove unread tags after reading
- important point
    - Suppose you read it and want to do some task.
        - Fixing broken notation or updating outdated information?
    - Don't think, "I'll remove the unread tag after I finish this task."
        - That's a different task from "reading."
        - It creates an extra state of "I read it, but I haven't untagged it because I have a task I want to do."
        - If it's something as simple as two minutes, just end it now.
        - If not, it should be tagged or pinned differently, or managed differently than unread management.
        - The list of unread pages should be in Date modified order.
            - When you stop reading, you can write down what you have read, and the next time you read it, it will be at the top of the list, and you can easily see how far you have read.
- If you're using [[Porter]], you can use Pin Board to pin unread pages.
    - Open unread pages immediately without going through the heavy top page
    - Removing unread tags is also a one-touch operation, as lines are cut by pressing the cut button without selecting a range.
- When the goal is not simply to read everything but to create a network of knowledge
    - You can write your own summary or keywords in link notation when you have read and unread it off the page.
    - At this time, Scrapbox's link suggestion feature can suggest other pages that you haven't read yet.
        - It's also good to read by following the links, because it's easier to create a network of knowledge by following the links than by mechanically reading from the top of the unread list.

Unread tagging script
python

```
import json
data = json.load(open("in.json"))
for page in data["pages"]:
    page["lines"].append("#unread")
json.dump(data, open("out.json", "w"))
```



---
This page is auto-translated from [/nishio/Scrapboxで機械的インポートコンテンツを全部読みたい](https://scrapbox.io/nishio/Scrapboxで機械的インポートコンテンツを全部読みたい) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.