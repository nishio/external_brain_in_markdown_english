---
title: "Examples of Broad Listening Applications within Cybozu"
---


On 2024-09-10 [[Cybozu]] used [[broad listening]] for internal workshops
Mr. Yasuno's broad listening broadcast on Nittele ([[Nittele NEWS x 2024 House of Representatives Election x Broad Listening]]) raised awareness, and there was some discussion on SNS that "broad listening is not limited to the public sector, but can also be used in the private sector. In fact, there are some cases where it is used in the private sector, so it is not a surprise to see it being used in the public sector. Here are some examples of actual use in the private sector

A workshop was held for 100 managers to understand and share the corporate culture (Culture) to improve teamwork throughout the company.
Workshop Objective: To foster a common understanding throughout the organization by allowing employees to speak in their own words and to share and deepen their understanding.

Workshop Content
- Individual work: First, write down individually the "behaviors" that embody the five corporate cultures.
    - To keep the discussion on the ground by focusing on concrete actions rather than abstract discussions
- Group work: 20 groups of 5 people each for discussion
    - Each group will be assigned a scribe who will not participate in the discussion and write a record of the discussion in [[kintone]].
- The minutes of the meeting will be visualized in [[Talk to the City]] and shared at the reception.
    - Five separate reports for each of the five corporate cultures
    - Tight schedule with data coming in at 3pm and report back at 5pm.

Example of output clusters
![image](https://gyazo.com/9b4032fbdf5f6bc7ccb007726aee6ed4/thumb/1000)![image](https://gyazo.com/402978df3e857b717039f3cccd1acffd/thumb/1000)![image](https://gyazo.com/9aa4d994d654e30c61c356c7cbd93eff/thumb/1000)
![image](https://gyazo.com/dd5834c36cc8addc73f499ea41d2f4c8/thumb/1000)![image](https://gyazo.com/2b626eff3a1fd3ec6972798f460e5ae5/thumb/1000)

Technical

On choosing kintone as a data source
- The weight of the factor that the target company is Cybozu and all employees have a kintone account is significant.
    - I initially thought the requirement was for 100 people to write out their individual work in parallel at the same time, and then promptly convert it to CSV for analysis, so I thought kintone was the way to go.
    - Finally, the "20-team minutes" were analyzed, so there was not much need to deal with concurrency.
    - The advantage of using kintone is that I don't have to do the work of bundling 20 cases, just exporting CSV.
    - For those who want to do a 100 person simultaneous parallel export workshop in the future, I would use Google Spreadsheet if you can't use kintone, because it can also export CSV.

Character code for CSV export
- In Japanese environments, Shift-JIS is often used for compatibility with non-Web applications such as Excel.
- The Talk to the City and OpenAI side assumes UTF-8, so you get the following error
    - `UnicodeDecodeError: 'utf-8' codec can't decode byte 0x91 in position 31: invalid start byte`
- With kintone, you can choose to output in UTF-8 here.
    - ![image](https://gyazo.com/c296965df13bc3999e4f434a64752e91/thumb/1000)
    - Google Spreadsheet should have a similar feature
- If you export the file in UTF-8, Excel assumes Shift-JIS and the characters are garbled. This problem can be solved by setting the file to "UTF-8 with BOM", but it may cause an error because TTTC is not implemented with "BOM" in mind.
    - In this case, instead of feeding the exported CSV directly to TTTC, I created my own Python script to do the preprocessing, so I absorbed it in that part.
py

```
with open(filename + ".csv", "r", encoding="utf_8_sig") as csvfile:
    reader = csv.reader(csvfile)
    next(reader)  # skip one line
    for row in reader:
        ...
```



Importance of pre-testing
- I generated virtual minutes in LLM and experimented with them beforehand.
- There were a number of things that didn't go according to the pre-experiment, but I'm glad I was able to reduce the amount of things I had to deal with on the day.
    - The above story about character codes is one of them, which I could have noticed and dealt with ahead of time by trying it out beforehand.

Azure OpenAI Service
- TTTC is supposed to hit OpenAI's API directly.
- It took a rather long time to switch to Azure OpenAI Service.
- Non-engineers may think "It's just switching, so it's easy," but it's not the kind of work that can be done for free, so if you do it on contract, you should charge extra for the API switching, +500,000 w
- I'd like to share this revised diff in a swell way.

parallel execution
- 5 reports were run in parallel.
- Five reports does not increase the time by a factor of five (because they can be executed in parallel).
    - Five Extruction were run in parallel and one died at Rate limit.
            - Be careful with [Rate Limit of OpenAI API
        - In this case, a rerun was OK.
    - The rest of the process is fine.
    - It seems to die for sure if the visualization part is executed at the same time.
        - We only need to re-run this one if it's dead, too.
- A scale of this size can be completed in 5 to 6 minutes without error.
    - In fact, it took 30 minutes from the time the data came in to the time I created and shared ver.1 of 5 reports (although I discovered the problem later).

[[TTTC:empty vocabulary]]
- Problems uncovered in pretests
- Errors that occur in clustering
    - > ValueError: empty vocabulary; perhaps the documents only contain stop words
    - I was rather troubled by the resolution.
- As of 2024-10-29, the source code for the version [[Nittele NEWS x 2024 House of Representatives Election x Broad Listening]] is available, so it would be easier to explain using that.

Formatting issues in the minutes
- Problems not uncovered in pretests
- The minutes generated by the LLM in the pre-test looked like this
    - > Yamada: Now let's begin a discussion about behaviors that embody the corporate culture. I understand that the theme is "sharing ideals. First, I would like to ask your opinion on how you all share the ideal.
    - >  Mori: As a legal department, our ideal is to minimize legal risk for the entire company. To achieve this, it is important that the entire department works together to uphold high ethical standards. To achieve this, we hold regular internal trainings and workshops.
    - >  Kobayashi: It is important to create ideals that we can share in the Creative Department as well. In particular, it is essential that we all share the same vision for success in order to generate creative ideas. In this year's campaign, we acted on the common theme of "pursuit of originality.
    - One important feature is that "one lump of speech is one line."
- The actual minutes were recorded in different formats by different scribes for each group.
    - Example: The
:

```
Mori: As a legal department, we minimize legal risks for the entire company.
　　The ideal is for the entire department to work together to achieve this goal. To achieve this, the entire department must work together to achieve high
　　It is important to adhere to good ethical standards. In order to achieve this
　　Regular internal training and workshops
　　Yes.
```

        - I should have explained in advance that it is not good from a data science point of view to have a line break in the middle of a word like this or to have full-width spaces for appearance.
- It's very troubling because the process was designed to chop and process line by line, assuming the characteristic of "one lump of speech by one person in one line."
    - As for the actual timeline, the data came in at 15:10, and once I finished making the 5 reports, despite my disbelief in their appearance, it was 15:40
    - I then investigated the cause of the disbelief and noticed the line break and full-width white space indentation in the above sentence at 15:42.
    - Developing code to cleanse this type of format into a one-by-one line format is the right way to go.
        - In that case, if it takes 30 minutes to re-run the report generation, we need to finish the development and pre-processing in 48 minutes.
        - Consider fixing it manually and spiritedly.
        - I considered this from a developer's perspective, but the indentation is also mixed, so in the end, if this is to be implemented as well, it is better to implement it with LLM than with an if statement.
            - If this is the case, we decided that it would be better to leave the extraction part to LLM than to develop a new one in a short time, and decided to consider "the whole minutes as one contribution" and prepare a report.
            - That got it to look decent in time, for a change, but
                - The "original view" of each point would give the entire minutes.
                - I think the number of points of opinion extracted has been dramatically reduced.

- [[TTTC's "detached island cluster" issue]]
- The reason for the remote islets is that the LLM is generating strange things in the original data in the first place, or it could not be extracted properly.
- If you get strange output, you need to run several iterations to correct the prompts.

Necessity of pretreatment
- As with the issue of the minutes format in this case, it may be better to expect a pre-processing process in between, as the data may not always come in a way that is suitable for the standard TTTC workflow

- [[Putting a place where good discussions can take place after visualization]]
- Better if this can be done.
- We could incorporate the discussion here and do a second round of visualization, etc.
    - It has been visualized and discussed several times in Taiwan vTaiwan.

Basically, it's easier to have an internal discussion than a faceless X/Twitter rant without the hassle of filtering out the rants, etc.
- But of course, there is a risk of filter bubbles when people in the same organization see the same thing.

---
This page is auto-translated from [/nishio/サイボウズ社内でのブロードリスニング活用事例](https://scrapbox.io/nishio/サイボウズ社内でのブロードリスニング活用事例) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.