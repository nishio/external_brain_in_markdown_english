---
title: "Visualization of Parliamentary Proceedings"
---

2025-03-06
An experiment to see how much human labor can be outsourced to AI

Initial DeepResearch
>  <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Look into how to get data from Japanese parliamentary proceedings, can it be done in Python or something?
>  I would like to know roughly what is possible to develop ideas.
Further DeepResearch
>  An API that can get JSON with GET is attractive, especially for keyword searches. Let's find out more about this API, gather information about what has been created using this API in the past, and describe "what is possible".
Next o3-high-mini
> I would like a script to read the above log and output it as CSV formatted data to visualize the discussion on a particular topic at a later stage. First, I need to compile the information needed to create that, and ask questions if I'm missing any information. The way to select "specific topics" is by keyword search against the agenda and statements, and the latter stage is embedding using LLM, so the main focus is on the statement data. It would be nice to have attribute data (speaker and political party) in an additional field in the CSV that would allow for conversation flow and additional analysis.
Further o3-high-mini
> Multiple keywords are retrieved by OR search, argparse, and specifying the time period is indeed important. Let's start with a short one as default, and try to make it gradually wider only when the number is small.
>  The CSV remark ID is an integer value with the name comment-id and the remark text in comment-body. The rest of the names can be appropriate.
>  argparse with filename/save location: default
>  Encoding: UTF-8 without BOM
>  Separator: comma delimited
>  Error Handling: Errors are OK for immediate death
>  Data cleansing: once without. I'll make something that works and then observe.
>  Can you make it with this? If you can make it, make it.

[https://chatgpt.com/share/67c9b1cb-3c14-8011-b4d8-7efe11d804af](https://chatgpt.com/share/67c9b1cb-3c14-8011-b4d8-7efe11d804af)

Run the generated script as appropriate.
> Searching for keyword 'earned income tax credit'...
>  <data><numberOfRecords>0</numberOfRecords><numberOfReturn>0</numberOfReturn><startRecord>1</startRecord></data>
>  JSON parsing failed
That's no good!

Give this log to Devin for implementation.
- They can't read the ChatGPT logs directly, I gave them a copy and paste.
- First, I implemented it in the style of parsing XML, saying "The Parliamentary Meeting Minutes API returns data in XML format.
- > <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Can't you make it JSON?
- Can't you do it in JSON? I asked, I checked the documentation and changed the parameters.
- > <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Try to see if you can set a time period for the keyword "income tax credit" to gather about 1,000 entries.

> <img src='https://scrapbox.io/api/pages/nishio-en/Devin/icon' alt='Devin.icon' height="19.5"/>After confirming that the JSON format support was working properly, we attempted to retrieve data using the keyword "income deduction" and retrieved 846 records. Since the target of 1,000 records was not reached, we decided to try again with a further expanded time period.

It's done.

> <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/> No need to support XML format, simplify scripts

> <img src='https://scrapbox.io/api/pages/nishio-en/devin/icon' alt='devin.icon' height="19.5"/>
> Test Results
>  I ran the test for the "Earned Income Credit" keyword in a simplified script:
>  python3 kokkai_api.py --keywords "income_deduction" --start-date "2006-01-01" --end-date "2023-12-31" --output "income_deduction.csv"
>  Results:
>  1058 records successfully retrieved
>  Simpler code while maintaining the same functionality as before

I tried to put it in visualization, but trouble.
- →I was wrong about the field information required by the visualization system in the latter stage.



As of 3/7, the latest data from the Library of Congress' Proceedings Search is 2/19, and there appears to be a 2-week delay

Published.
- [nishio/kokkai_api: script to retrieve parliamentary proceedings API](https://github.com/nishio/kokkai_api)

---
This page is auto-translated from [/nishio/国会議事録可視化](https://scrapbox.io/nishio/国会議事録可視化) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.