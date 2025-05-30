---
title: "Import Scrapbox projects into Kozaneba (Development)"
---

from [/villagepump/Scrapbox project imported into Kozaneba (development)](https://scrapbox.io/villagepump/Scrapbox project imported into Kozaneba (development)).
I know it's not a quick story, so I'll leave the thought process here.<img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>

Since the Kozaneba sample code has "Create JSON for Kozaneba from source code", I thought I could use this to create JSON for Kozaneba from JSON exported from Scrapbox
- There was no link information in the escorted JSON.

The premise is "import links between pages as arrows in Kozaneba" specification
- I can still do it because it's as a discrete element without lines.

Hit API on each page to get link information?
- I believe there was an API to get a list of pages with link information.<img src='https://scrapbox.io/api/pages/villagepump/inajob/icon' alt='/villagepump/inajob.icon' height="19.5"/>
    - [/scrapboxlab/api/pages/:projectname/search/titles](https://scrapbox.io/scrapboxlab/api/pages/:projectname/search/titles)
    - But this doesn't have the text.
    - If it is a case of creating from exported JSON, the body text is at hand.<img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>
        - or rather, from Kozaneba's point of view, I wouldn't use the text.
            - It wasn't like that. Oh well.
            - When you add it via the UI, it hits the API at that point to get the description.
            - Once you do it with empty description
                - think about later
    - This looks good.
    - I just used it the other day when adding a well completion feature to inline.
    - I looked at the responses, this looks good.<img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>
    - Red link should be included, well, even if there is one.<img src='https://scrapbox.io/api/pages/villagepump/inajob/icon' alt='/villagepump/inajob.icon' height="19.5"/>
        - Not sure if it would be more interesting to have or not.<img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>

For now, I'm trying to experiment with a project of about 100 pages, so all pages are fine.
- But in general, people who try to use this feature when it is released are only going to have a [[furball problem]] if they do it in its entirety, because there are 10,000 pages or something like that.
- I think it is most useful to specify a page and target only those linked to that page in one hop.
    - Specify and load pages that seem to have exceeded 100 links.
    - That way you can see the links between the child pages and help separate the children into groups.
    - If it were this use case, I wouldn't draw the link from parent to child because it's obvious.

Things that may or may not be useful or interesting
- Display the results of following a random link from a specified page (or random page) about 100 times.

[/scrapboxlab/api/pages/:projectname/search/titles](https://scrapbox.io/scrapboxlab/api/pages/:projectname/search/titles)
- Title.
- I have the image URL.
- No text.
- There is no URL for this page itself.
    - Would space replacement and URL encoding help?
- The link information is the title of the page you're linking to.
policy
- Since it is not a large amount, create the vertex set and the edge set in a straightforward manner.
- whether or not to make it a directed side
    - I can do that, but I don't know how to display the two-way ones.
    - I'll take both arrows.
- Possible endpoints that do not exist in the page list due to inclusion of red links
    - Let's add the destination of the red link as a Kozane!

Red link, there were more Ws than expected.
- ![image](https://gyazo.com/6ae926fccbf166fc262b27369345056d/thumb/1000)
    - I'll stop importing red links.

Well...
- ![image](https://gyazo.com/58d2bdca9ff75cb0dedd5a34949a0996/thumb/1000)
- Actually, the physics engine is implemented.
    - ![image](https://gyazo.com/9d1baef134a404e4f21f2fece6cea622/thumb/1000)
    - I haven't found it very useful, so it's not in the official documentation. w

- Hmmm, mankind has yet to invent a solution to this furball problem...
    - ![image](https://gyazo.com/9b479212a7920bf6eb07dec777d861cb/thumb/1000)
    - It's obvious to the point where you can move something that is isolated or put something that is only connected to one thing beside it.
    - From there, it suddenly becomes a conundrum.
        - Even I, who have many times KJ method experience with hundreds of cards, have difficulty in unraveling this 100-card hairball!
    - Let's remove the chat page from the link, which is a giant hub.
    - Oh, Scrapbox Kozane doesn't have a leave from lines menu...
    - Well, the import is done, and we'll continue tomorrow.
    - Oh, well, you can do the same thing by cloning and deleting.
        - You don't even have a clone on your Scrapbox Kozane!

memo
- Page 99
- 400 links


---
This page is auto-translated from [/nishio/ScrapboxプロジェクトをKozanebaにインポートする(開発)](https://scrapbox.io/nishio/ScrapboxプロジェクトをKozanebaにインポートする(開発)) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.