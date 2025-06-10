---
title: "Narrow down your search with Looker Studio"
---

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Can Looker studio allow users to switch the value of the prefecture in the original data of the graph to see the filtered results?
<img src='https://scrapbox.io/api/pages/nishio-en/o3/icon' alt='o3.icon' height="19.5"/>
1. drop-down list (recommended)
- Verify that the data source has a prefecture column (Dimension)
- Open the report in edit mode and select "Add Controls" → "Dropdown List" from the toolbar
- Specify "Prefecture" in Properties > Control field on the right
- Set options to your liking, such as "Allow multiple selections" or "Show search box
- By default, all charts on the same page are affected, but "Apply filter to" can be used to apply the filter only to specific charts.
Viewers can now simply select a prefecture from the pull-down menu to see a graph narrowed down to the relevant data.

![image](https://gyazo.com/05177f9e98b3cbc68a6fd792fb461693/thumb/1000)
- It's done.<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
    - [[Looker Studio]] That's convenient.
    - ChatGPT is also useful, which will tell you if you ask.

Registered Volunteers by Prefecture] [Registered Volunteers by Team Mirai Prefecture

---
This page is auto-translated from [/nishio/Looker Studioで絞り込み](https://scrapbox.io/nishio/Looker Studioで絞り込み) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.