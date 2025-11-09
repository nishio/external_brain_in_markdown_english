---
title: "Regular Hearing AI Development: Insights from Team Mirai's Activities"
---

Regular meetings of [[Hearing AI Development]]: What we have learned from the activities of [[Team Mirai]].
[https://docs.google.com/document/d/1plggszRTxEEYUcZuCLiHkPrBsMtxr3RQpctKtZe5y4M/edit?tab=t.0](https://docs.google.com/document/d/1plggszRTxEEYUcZuCLiHkPrBsMtxr3RQpctKtZe5y4M/edit?tab=t.0)

2025-07-30
Summarize what we have seen from Team Mirai's operational experience
- (I wrote some of this in Slack, but I thought it would be better to summarize it in this document, so I reprinted it/recognize that some of it is in Issues and some of it has already been implemented).
- I was just writing down what came to mind, and it got really long, so maybe we can have them do whatever needs to be discussed first, and then we can do it in the remaining time.
- To explain Nishio's role, after Kakuno-san set up the instance, he got access to the management screen and used it as a user in charge of data analysis.
- PR data analysis for the policy team and X analysis for the PR team do everything from data acquisition to analysis.
    - Case Study: [[Team Mirai Upper House Election 2025 Wide Hearing AI]].
- AI An's question analysis receives data from AI An's team and analyzes it.
    - Case study: [[AI anna→Public hearing AI]].
- Another analyst has been added after the election to analyze the supporter team's KPT reflections.
    - This probably won't be shared outside of the supporter community.
    - Talk about observing non-developer users as they begin to use it.
    - I ran it on my end and shared the report with ngrok, but I was walking on a trap that PC or ngrok was dead and I couldn't share it, then I gave him the URL and pass for the admin panel and it was working fine.
    - Feeling that we don't currently provide supporters with access to the administration screen, but may do so in the next election.
        - I think the current "pass admin access = see all unpublished reports" will be a hurdle to doing that.
        - It's important to have user management if you want to do something like "only those who created it can see it".

About the Display
- I would like to be able to display the "original data before extraction" in a similar way to turning on "link" (X prohibits redistribution, so this is disabled, but there are times when I want to see the original data without a link if I want to insert and analyze data that is not so redistributed).
    - I'd prefer "click for modal view."
- Regarding the smartphone view, still concerned about the issue of poor default appearance when real users post on social networking sites.
    - I thought it would be difficult to solve the problem drastically and left it until now, but now I have an idea of "share while zoomed", which is implementable and could solve the problem so-so.
    - In other words, "Since it is impossible to set the default to show the entire screen in smartphone view, it would be better to be able to decide where to show the screen as the initial screen when in smartphone view".
    - (Added now, after some time since this discussion) I wonder if this resolution is a good idea.
        - I've had instances where "users of the broadband AI were hesitant to post the report URL on social networking sites because they were concerned that when they shared it on social networking sites, people who viewed it from their phones would be "gobsmacked."
        - It would be absurd to provide full functionality on the small screen of a smartphone, so it might be better to return a simplified screen and do something like, "For details, use the PC screen.
        - The organization that created the report wants to share it on social networking sites, but the problem is that many people on social networking sites are looking at it on their phones, so they see a broken screen.
            - →Share is not controllable as the user does it, and the smartphone view is necessary.
            - Or encourage people to hold their phones at least horizontally.
            - If the requirements are more specific, designers can think about it, but it's too difficult to manage everything.
            - Is it appropriate to produce a scatter plot of 30,000 cases for smartphone users?
            - Maybe it would be nice to be able to create a smart phone view after the report is created, because that's a feature that will be needed after the report is created.
    - [[Asahi Shimbun Broad Listening]] I saw the case study and thought, well, there are cases I want to embed in other services.
    - I'm also going to be experimenting with a new service once I've embedded a report created by a broadband AI into the new service.
    - I am going to try to create different views for "deep opinion groups" and "hierarchical views" while still using the data.
    - Maybe we could make a report and then say, "Let's make this component.
        - Hierarchical display is like an outliner.
    - Postscript: 3 weeks later: [[Regular Wide-ranging AI Development: Trial and Error in View]].

Convenience of management
- Team Mirai's admin screen, 61 reports, hard to scroll through, I want the newly created one to be on top (just a thought note).
    - I think you will want to organize it in some way when multiple departments start using it (maybe add tags and a screen to filter by tags).
    - If the House of Representatives election starts while using the current instance as it is, I'm going to want to bundle up the current reports and shove them in a folder with "House of Councillors Election 2025" or something like that.
    - I considered the option of exporting all the data as of the time of the Upper House election and setting up a new, clean instance, but then there is the question of what to do with the published reports.
        - It's a hassle to think about moving only published reports to a new instance.
        - Maybe export the data, back it up, and then delete it from the server.
        - Capacity won't be an issue, so it's going to be easiest not to delete data if it solves the problem of the index filling up and making it harder to work with.
- There was a problem with the default prompt to extract "opinion", which targeted the question text but extracted opinions.
    - Now that I have a more concrete example of the abstract "we need to change the prompts depending on the situation," I'll put it into language.
        - I want to extract only the "criticism" from X's post and observe
        - I want to extract only the "sense of the problem" (what the proposer feels is the problem) from the policy pull requests.
        - I want to extract only "questions" from the questions to AI Anne's ("Great! and so on are removed)
    - At the moment, I'm tweaking the prompts, but I think it would be better to have a support tool since it's quite a hassle to change the "fewshot example" to match the prompts.
        - Rather than having users directly use the support tool itself, it would be easier for them to select a few typical use cases as presets based on my trial-and-error experience.
        - The purpose is that it might be too difficult to change all 4 prompts at once, so it would be nice to be able to select from the presets and change them all at once.
    - I did another experiment on this subject to extract awareness of the problem with preprocessing.
        - > [nishio](https://x.com/nishio/status/1950464289552367894) Based on the proposals (pull requests) received for Team Mirai's manifesto, we extracted and analyzed the awareness of issues that the proposers have.
        - >  This is the first step into the future, and we plan to improve the system side to utilize this data in the future.
        - >  ![image](https://pbs.twimg.com/media/GxFwbvFbUAEhr9m?format=jpg&name=medium#.png)
                - [[Team Mirai Problem Awareness Spreading AI]]
        - 18967 problem awareness extracted from 9688 PRs
        - With gpt-4o, total API usage: $32.094862
        - When these results were put directly into the broadband AI, an additional 21348 EXTRACTIONs were made from the data of 19867 cases.
            - Might be better to skip the EXTRACTION (that feature is not available right now).
            - If there is an implementation that only does the post-processing after the already-extracted data is given, I think it would be possible to realize the long-sought "I want to reuse the report" (I think in many cases, the heaviest part in terms of cost and time is the extraction, so I would like to reuse that part).
            - The good thing is that the size of the report is reduced by the pre-processing extraction before extraction, which reduces the cost of reworking the report with a broadband AI (I don't recommend this approach because it is too bad-know-how, but the system needs to be improved).
- Automation of report generation with API
    - It's easy for non-engineers to set it up on the admin screen, but honestly, when I'm working a lot as an engineer, I want to send JSON to the API and start processing.
    - I've confirmed that this is feasible, so I feel like I'll organize the code and provide it as sample code later.
- Later editing
    - I want to edit the slug as well as the title and description.
    - You want to clean up the URL when you publish it, not when you preview it internally.
    - Hesitant to make a clean URL for public use because of the possibility of changing parameters for review during the internal preview phase.

I think there are a lot of "things I experienced but couldn't verbalize" even though I wrote down roughly what came to mind.

- [[public information AI]]

---
This page is auto-translated from [/nishio/広聴AI開発定例:チームみらいの活動から見えてきたこと](https://scrapbox.io/nishio/広聴AI開発定例:チームみらいの活動から見えてきたこと) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.