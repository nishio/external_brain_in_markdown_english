---
title: "Regular Wide-ranging AI Development: Trial and Error in View"
---

[[Regularly scheduled AI development]]:Trial and error of view
[https://docs.google.com/document/d/1plggszRTxEEYUcZuCLiHkPrBsMtxr3RQpctKtZe5y4M/edit?tab=t.0#heading=h.8trp8dyjifr6](https://docs.google.com/document/d/1plggszRTxEEYUcZuCLiHkPrBsMtxr3RQpctKtZe5y4M/edit?tab=t.0#heading=h.8trp8dyjifr6)
public information AI

2025-08-20
Trial and error on what kind of information presentation should be possible by fixing the data side (for 3 weeks)
- You can see it here: [https://policy-pr-hub.vercel.app/](https://policy-pr-hub.vercel.app/)
- Repository here [https://github.com/team-mirai-volunteer/policy-pr-hub/](https://github.com/team-mirai-volunteer/policy-pr-hub/)

Problem of aspect ratio changing with the size of the drawing area -> fixed
- ![image](https://gyazo.com/86105b223d96db8f243fbc0bdf204ea9/thumb/1000)
    - This is the correct aspect ratio, which has been stretched until now.
        - [[p broadband ai-2025-08-12]]

Problem that it is difficult to understand that the dark opinion display is a partial extract of the overall scatter plot -> filtered data is displayed as small dots instead of hidden
- ![image](https://gyazo.com/27955affe4f412b410809ba27bd327e1/thumb/1000)

When there are many labels, labels overlap in clusters and are difficult to read → drawer lines
- ![image](https://gyazo.com/e0f48877fe8880debe93a37f2806d74c/thumb/1000)
    - With this display, 20 labels is the limit, and at 30, you'll feel like you have to put them on the top and bottom as well.
    - The dark cluster display shows 80 cases in 20% of the 400 cases in this data. I don't think it would look right even if it were on a pull-out line.

An approach that produces a diagram of a region rather than a distribution of points
- Instead of Mr. Nakayama's suggestion of concave hull, I tried to fatten the radius r
- The collision area is [[Voronoi division]].
- ![image](https://gyazo.com/1c903d71a5e672c27e4f6c178a1a37fb/thumb/1000)
    - In fact, one area was supposed to be one polygon to save weight, but currently the polygons are failing to merge.
    - Hangs for 7 seconds for pre-calculation, need a mechanism to pre-calculate and cache on the server side

Problem of hierarchical display UI not being intuitive and unnoticeable when digging deeper -> Outliner-like hierarchical display
- [https://policy-pr-hub.vercel.app/hierarchical](https://policy-pr-hub.vercel.app/hierarchical)
- ![image](https://gyazo.com/ad5363d0527d9df0706806e22efb7c0a/thumb/1000)
- Click to open
- ![image](https://gyazo.com/402492074c39bb3ba7761cf09cfb3a20/thumb/1000)
- Open child element
- ![image](https://gyazo.com/76fe9135cec0a7630ff0b0d7af04bcb3/thumb/1000)
- Open further
- ![image](https://gyazo.com/d40535ceb16cb5b52ea89a3c60f52f41/thumb/1000)
- Display individual data
- ![image](https://gyazo.com/0ef0884e5c09ca2ea36cec3edfb8b688/thumb/1000)
    - A link to the data from which the data was extracted is attached on the far right.

Shouldn't the same style be used to display strong opinion groups?
- [https://policy-pr-hub.vercel.app/hierarchical-clusters](https://policy-pr-hub.vercel.app/hierarchical-clusters)
- Sorting display of clusters by density
- ![image](https://gyazo.com/99247cb0684e404de74e9fa499f079d1/thumb/1000)
- A strong opinion group is, in essence, looking at only the top 20% of this list.

A comb that lets you know where your opinion is categorized
    - [[Opinion traceability has two directions.]]
- Nowadays, the broadband AI has traceability in the direction of the "original post" from the "final report" and can thereby show that what is written in the report is based on the opinion of "someone else".
- However, there is no traceability in the direction from the "original submission" to the "final report" and no way to know where "I" wrote the content went into the report
- Requires traceability in both directions
- ![image](https://gyazo.com/37f8dd0b4c1906f2ca94a7713da2b0ee/thumb/1000)
    - For now, we have made it possible to search by entering IDs; we need a more convenient system for general users.
        - I'd like to see a list of "your suggestions" and from there I can jump to the individual suggestion detail page, where I can see how the suggestion was handled and where it went in...

Mechanism to use the results of the public hearing AI as a basis for deliberation.
- Currently, "visualization is the end of the story.
- I'm hoping we can vote for and against the cluster and discuss it.
- This is [[Your Priorities]] target.
- ![image](https://gyazo.com/d566903fbcc1b957b23371b0bb3be006/thumb/1000)
- People can vote yes and no and write in their reasons (maybe limited to one per person)
- Submissions can be upvoted/downvoted (only from the same camp?).
- The sorting by approval/disapproval ratio has now been implemented, but the approval/disapproval vote itself has not yet been done, and the assumption is that the person who created the PR is in favor of the PR, so it is counted as an approval vote.
- ![image](https://gyazo.com/295d28ce71db67107d6a5b0a3a2fd360/thumb/1000)
- Doesn't this sound like an addition to the broadband AI?
    - Yes, talking about using the data from the analysis to do more than just look at it.
- Clearly speaks to what the current broadband AI can do -> one way to use the data produced by the broadband AI.

Notes on thoughts
- Maybe we need an "Admin Report Screen"?
    - Now it's like this.
        - Reporting Screen: Admin
        - All Reports List Screen: Admin
        - LISTED REPORTS LISTING SCREEN: Anyone
        - Report Screen: Anyone
    - Switch between various views on the administrator's report screen, change default settings, etc., and then "publish with these settings".
- When I think about smartphone compatibility, I feel that presenting information in hover is a bad idea in the first place.
    - It is not correct that mouse hovering over a cluster brings up a detailed description of each point of the components, but it is correct that mouse hovering over a cluster brings up the details of the cluster and clicking on it brings up a narrowed-down view of that cluster (but requires a back button).
    - Putting in the HOVER listener seems to be the cause of the performance degradation in the PC version as well.
    - Basically, should the menu appear when you click or tap on it?
- I feel like the hierarchy should increase dynamically to keep the screen design within a decent viewing range.
    - Because it is limited to two layers, it is necessary to divide the data into 20 labels in one layer when there are 10,000 data or so. Essentially, the upper limit of labels that can be drawn is determined by human cognitive ability, and it would be correct to increase the number of layers when there is a lot of data so as not to exceed that limit.
- Isn't it necessary to have the number of clusters pre-set?
    - You can decide on the cubic root after EXTRACTION.
    - Right now, I've made the value pre-determined as a required field, but it would be nice to make it the default value of "leave it to me" and only those who want to customize it should be able to set it.
    - tokoroten: I feel that the default value is not enough for the number of clusters I am using, so I think it would be good if there were more, normal, or less clusters, even if it is a recommendation.
    - nishio: "roughly", "in detail", or "very in detail" might be good?
    - I don't remember what the default value was, but I think 30 for the first stage, 900 for the second stage, and 27,000 for all data are the limits of what a human can endure with the current system.
    - The analysis itself can be done with more, but without increasing the hierarchy, human cognitive abilities are in trouble.
    - Aside from that, it may be easier to be understood than to do a lot of things if you explain the strength of the listening AI as the ability to quickly summarize 20,000 data items into 30 items and then dig deeper as needed.

---
This page is auto-translated from [/nishio/広聴AI開発定例:ビューの試行錯誤](https://scrapbox.io/nishio/広聴AI開発定例:ビューの試行錯誤) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.