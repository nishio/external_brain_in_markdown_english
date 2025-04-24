---
title: "Automatic Translation System 2025-03-02"
---

- Repairing an automated translation system that I don't know how long it has been out of service.
- I don't know how much work we did last time...
- It's not good enough to find them because they don't have names on them.
- When I search to find it, I see other work-in-progress tasks and get distracted.
        - [[2024-09-08External brain GitHub work]] (A)
        - If you have Cosense -> GitHub (Markdown) to begin with, you can easily read Roo Code and Devin.
            - No search on Cosense but grep locally.
        - This is a side street, so hold off.
- [[etude-github-actions]]
    - [[Diary 2025-01-09]]
    - > There are some local changes, I don't know what these are...
- Let's just check this out for now.
- ![image](https://gyazo.com/e46fa4514beb436903ebc6501bd05271/thumb/1000)
    - There is an error trying to Import to Scapbox after committing, so I have the latest translation results.
        - It's a move to put this Japanese version and the English translation into GitHub for now -> (A)
            - This is a side street, so hold off.
    - Is this the "why error on import" problem that has been occurring a few times?
- ![image](https://gyazo.com/85130a94d34679a90dac48570dd10b70/thumb/1000)
    - Devin's unfinished task, forgotten without being reviewed.

- I was a little distracted.
    - [[Discussion #67c3f522aff09e0000edf142 via llm]].

- ![image](https://gyazo.com/972d432d35972194740045b704e4b1b2/thumb/1000)
    - You're getting an error on the import of about 68 pages to begin with.

- (A), but "I kind of think we should quit [[importing to Scrapbox]] already.
        - [[2024-11-17 external brain thinking]]
        - That pretty much says it all.
        - > /nishio-en will not be updated as it is, and when it works with GitHub Pages, I'll pin the "see here" page and be done with it.
        - I think this policy is fine.

- I remember doing something with Quartz after that.
        - [[Hosting of Cosense English Translation 2024-11-24]]
        - Oh, this one.
        - [[Machine Translated Scrapbox Published in Quartz on 2024-11-24]]
        - We got as far as publishing it on Quartz, but it was subtle.
    - Repository is nishio/from_scrapbox
    - Quartz as a component is forked from the original in nishio/quartz.
        - There's a possibility of customizing it.
    - I put the build result in nishio/quartz_deploy instead of nishio/quartz
    - We have achieved a situation where the English translation version is deployed in GitHub Pages, but there are some puzzling points, such as the display of backlinks by Quartz, and we stopped at the larger decision of whether to debug Quartz or whether it would be better to discard such a subtle thing. We're still there.

Time is running low for the rest of the day.
- Regarding the initial issue of broken automatic English translations, the automatic English translations are not broken and JSON importing has stopped.
    - I'm not going to devote an effort to fixing this.
    - It makes no sense to build a system based on an internal API in the first place.
    - Manual import of the latest
    - When an automated migration destination is available in the future, link to "Migration destination here" and stop the process.
- About the proposal to convert JSON to Markdown and then to static HTML with Quartz and distribute it via GitHub Pages.
    - It's done, but the HTML that Quartz produces is subtle.
    - In terms of (A), just being placed on GitHub at the Markdown stage has usefulness

- [[Push to other repo with GitHub Actions]]

It's done.
- [https://github.com/nishio/from_scrapbox/actions/runs/13614264620](https://github.com/nishio/from_scrapbox/actions/runs/13614264620)
- I checked and it wasn't done.
    - You're just continuing on when you get an error.
- This time it's done.
    - [https://github.com/nishio/from_scrapbox/actions/runs/13615083590](https://github.com/nishio/from_scrapbox/actions/runs/13615083590)
- It's in Markdown and on GitHub.
    - [https://github.com/nishio/external_brain_in_markdown/blob/main/pages/自動翻訳システム2025-03-02.md](https://github.com/nishio/external_brain_in_markdown/blob/main/pages/自動翻訳システム2025-03-02.md)

summary
    - [Cosense updates are converted to Markdown daily and entered into GitHub


I'm having Devin read it immediately.
- ![image](https://gyazo.com/e9c6e1d55ddfd1de1847663c2ce69448/thumb/1000)
- The atmosphere seems to be able to give a keyword and summarize it by reading all over Cosense about it.
- Results [[Evolution of the Scrapbox translation system by Yasukazu Nishio and the evolution of its philosophy]].


For import, try to import manually.
![image](https://gyazo.com/1ad374cbe6fabd554668045fa776240f/thumb/1000)
Could this be the cause of the error?

Have miscellaneous correction scripts implemented.
![image](https://gyazo.com/916d125f50269dd4abfa983373521fa0/thumb/1000)
Fixed.

![image](https://gyazo.com/f5d7c9b05c423bfb1e3cc8efc815097b/thumb/1000)
I can even copy files now.
- Might be useful when porting from a private project to a public project?

Notes:.
- I created a program to merge identical titles.
    - [https://github.com/nishio/etude-github-actions/blob/main/merge_same_title_page.py](https://github.com/nishio/etude-github-actions/blob/main/merge_same_title_page.py)
- [[translated into the same string during the translation process]] I guess...
- If I run this and then do a diff, can I import without problems?
    - Conversely, until now, the same title has been overwritten.

2025-03-03
<img src='https://scrapbox.io/api/pages/nishio-en/Devin/icon' alt='Devin.icon' height="19.5"/>
- Workflow modifications:
    - Added a new step to the nishio_trans_commit.yaml workflow to merge pages with the same title after creating diffs and before committing.
- Fixing merge scripts:
    - The merge_same_title_page.py script has been modified to process the data_en_diff.json file.
    - The script detects duplicate titles without regard to case and merges pages with identical titles.
    - The merged page is based on the most recent page and combines the contents of all pages.

I feel like you should merge and then take a diff.

[/nishio-en/Way of thinking](https://scrapbox.io/nishio-en/Way of thinking)
- This has en on it, but it's been translated, why?

Use of the "why?" style of asking about unexpected behavior, rather than telling people what to do. style of asking "why?
![image](https://gyazo.com/f2b7370c3f54ceafbec85059e8298a64/thumb/1000)
![image](https://gyazo.com/4b1be491d2be64799d21d2fbe39eb7e3/thumb/1000)
I'm impressed that you're checking the en description page.
And the conclusion, "We thought we had it implemented and used it, but we hadn't implemented it yet."
After this, he suggested, "I think it would be good to implement it this way," and I instructed him to "do that."

---
The confusion level is rising, so I turn the wheel in the direction of folding the task.

I got into trouble on an off-topic part.
I split the branch because it's hard to see the commit log when updating data in MAIN.
I thought it was working, so I further divided the GitHub Actions into two parts: what's working and what's not.
There was data that was not shared between the different actions, so I tried to commit it.
I found out that I forgot to set -e, even though the first "split branch" was not successful in the first place.

Fundamentally, if you split a branch because the data is not just overwritten but "diff'd from the previous branch" is processed.
"The code is up-to-date with main, the data is up-to-date with auto-update, what do you do?"
I'm not sure I've thought this through... I didn't think this through...

<img src='https://scrapbox.io/api/pages/nishio-en/Roo/icon' alt='Roo.icon' height="19.5"/>
We now have an overall picture of the problem. The following points can be attributed to the problem
...
Processing diff_json.py:
- Compare previous data (nishio/data_en_prev.json) with current data (data_en.json)
- Extract only the pages that have been updated and save them in data_en_diff.json
Issues:
- Separate branches, so main branch and auto-update branch have different data statuses.
- Differencing process compares previous data with current data, so if the branches are different, the differences will not be correct.
- In nishio_trans_import.yaml, the auto-update branch is checked out, but this branch does not always have the latest data

Think of a solution:
- Review of branch strategy:
    - Manage data and code in the same branch
    - Or, change the data differencing process to a branch-independent method.
---
Second opinion on Roo Code's opinion on ChatGPT o3
<img src='https://scrapbox.io/api/pages/nishio-en/o3-mini-high/icon' alt='o3-mini-high.icon' height="19.5"/>
I think the proposed solution is reasonable.
- The major advantage of single-branch operation is that code and data can be managed in the same state, preventing inconsistencies in the differencing process.
- Enhanced error detection (addition of set -e) improves reliability by allowing early detection and response to failures.
- If branching is to be maintained, a good mechanism for synchronization and data sharing among workflows must be in place, but the cost and risk of implementation should also be considered.

Overall, we believe that a single-branch strategy is preferable for a simple operation, and the proposed method is an effective approach.

---
It's all fixed.

Now the automatic translation system, which had been stopped for a while, is back on track.

The one I was writing today is also being translated into English.
[https://scrapbox.io/nishio-en/Automatic_Translation_System_2025-03-02](https://scrapbox.io/nishio-en/Automatic_Translation_System_2025-03-02)

---
This page is auto-translated from [/nishio/自動翻訳システム2025-03-02](https://scrapbox.io/nishio/自動翻訳システム2025-03-02) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.