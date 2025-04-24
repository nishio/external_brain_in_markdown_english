---
title: "AI Task Management 2025-02-27"
---

- [[AI Task Management]]
- [[AIPM]]

---
thinking
If it's an independent output and duplicated, it's more important.
- So if I do "not do it now," will it go down?
- It is inappropriate to lump them all together on a one-dimensional axis.
- I think it would be better to add, "On what date we decided not to do it now.

---
Adding tasks and updating tasks is not very easy.
- I like the fact that the AI can look at the backlog of tasks and say a lot of things, but I'm not sure I'm comfortable with where to update it.
- Well, I tried to do it with jsonpatch and that didn't work, and I haven't found a good way to do it yet.
        - [[jsonpatch didn't work.]]
- The person who made it forgot about it, so I asked AI and he told me, but it's a very subtle design.
- > New tasks are added using the script ai_project_manager/scripts/append_tasks.py. This script adds new tasks described in ai_project_manager_data/tasks/new_task.json to backlog.json. The task will be added.
- Ah, well, the prototype is made by the force of rewriting JSON by an AI agent that has coding skills to begin with, so the connection from OpenAI, which doesn't have those skills, is not a good one.


Let Devin create [AIPM WebUI

I've been thinking of "[[training gibs]]" and mainly having Devin write it instead of writing it myself.
- but I also thought, well, if you don't use Devin, [[Roo Code]], [[Stressful multitasking state to begin with]] and [Bet it all on CLINE [https://zenn.dev/mizchi/articles/all-in-](https://zenn.dev/mizchi/articles/all-in-) on-cline] (I use Roo Code), and I thought I should pursue both scaling out with Devin and scaling up with Roo Code.

Various errors due to clutter in tasks.json.
- I was OK with the ID being blank, but then I got the bug caused by that.
    - I forgot to do this because LLM is not very good at generating IDs, so I thought I'd generate an empty one and fill it in later.
- I wrote a script that generates a task
    - There is an uninformative field "type: "task
    - Maybe you should add created and updated?
    - If you update the "updated" status of the "done" items, you can see the recently done items in the "done" list, right?


![image](https://gyazo.com/798c8c8fb3e9c0e097988e8ce18cabf7/thumb/1000)
- Mostly made by Devin.
- I was going to have them just load the files, but somehow they even built a search function.

I forget what I wanted to do when I could have a concrete screen.
If you modify it yourself by watching the o3 output and observing its behavior, rather than having Devin edit it
- When I see the output and think "that task is done", I call mark_done.py
    - Then we should be able to DONE from the output.
- If I don't understand by just looking at the output, I call show_tasks.py
    - It would be nice if this could also be displayed by clicking on the output
    - Being able to see several at once is useful.

The addition of the task was subtle even in its current state.
- For now, I created a script that receives and creates only the minimum necessary title and description.
- The description could also be empty.
    - T/O on the title then.

-----
2025-02-28
editing capability
[feat: make tasks editable (issue #51) by devin-ai-integration - Pull Request #53 - nishio/ai_project_manager [https://github.com/nishio/ai_project_](https://github.com/nishio/ai_project_) manager/pull/53]

Test cases should be added before adding more and more features to the UI.

[Issue #52: Create server tests by devin-ai-integration - Pull Request #54 - nishio/ai_project_manager [https://github.com/nishio/ai_project_manager/](https://github.com/nishio/ai_project_manager/) pull/54]


A friend of mine used to tell me that he first learned the history command and then read desperately what his seniors did to learn it (over 20 years ago).
Right now I'm looking at the log of the flow of Devin creating a test environment in Playwright and saying "I see..." w

If you get stumped, ask o3 and he'll be kind enough to help you out.
> <img src='https://scrapbox.io/api/pages/nishio-en/o3-mini-high/icon' alt='o3-mini-high.icon' height="19.5"/>In the case of the npm script, npm automatically refers to playwright in the local node_modules/.bin. However, if I run "playwright test" directly in the shell, I get an error that playwright is not installed globally, it does not exist in the path, and the command cannot be found. The solution is to use the npm script or run "npx playwright test".
I see...

Well, the test case you wrote doesn't pass at all, but that means that Devin and I have different perceptions of the environment prerequisites, so I think it would be better to squash that early on.

Conclusion, my environment is not a CI environment, so when there is already a server on localhost:3000, I reuse it = read production data, not test data.
playwright.config.js

```javascript
 webServer: {
   command: 'npm run dev',
   url: 'http://localhost:3000',
   reuseExistingServer: !process.env.CI,
   env: {
     USE_TEST_DATA: 'true',
   },
 },
```


Regarding >ai_project_manager's server, let's create tests so we can easily test it in Playwright!
>  I would need the sample data and the environment variable options to test with the sample data.
I just wrote in Japanese, "USE_TEST_DATA", and it was implemented by using the environment variable USE_TEST_DATA and dividing the data by the contents of the API to be loaded, which is very helpful.

All tests now pass (I removed the fundamentally bad tests).

Shaping in the direction of cutting as AI makes guns.
- I've hidden the search mado that I don't need from the UI you made yesterday.
- I've also deleted the test cases you made this time that I didn't need.

I'd like to make this test run on CI... or something like that.
If I start here, I'll say "I'm almost ready to move" again, and then it'll be late at night and my health will suffer, so I won't do it.

---
Explain specifications in [[Advanced Voice]] while washing dishes.
- Cannot share directly ([https://chatgpt.com/c/67c1ddca-64a0-8011-bc4d-ab708bc6b2ce)](https://chatgpt.com/c/67c1ddca-64a0-8011-bc4d-ab708bc6b2ce))
Let o1 read it and make it happen in the issue.
- [https://chatgpt.com/share/67c1e586-c5c4-8011-91b1-28527707730d](https://chatgpt.com/share/67c1e586-c5c4-8011-91b1-28527707730d)
Answer the questions and submit the issue.
- [Implement the ability to highlight and click on task IDs in Markdown and display task information in the sidebar - Issue #55 - nishio/ai_project_manager [https://github.com/nishio/ai_project_](https://github.com/nishio/ai_project_) manager/issues/55]
Send it to Devin to have it implemented.
- ![image](https://gyazo.com/636cc0c7ab1008fb8ec2bf98b030f2fa/thumb/1000)
- I'm going to test it tomorrow, but from what I see on Devin's screen, it looks like it's working.


2025-03-01
![image](https://gyazo.com/d830736bb2a71ab4b7a3b4313f387fad/thumb/1000)

[https://github.com/nishio/ai_project_manager/pull/56](https://github.com/nishio/ai_project_manager/pull/56)


Files are not updated when done to a task in the sidebar
This is because the handler is not passed and is undefined.

When you press done, the file should be updated and the task should disappear from the sidebar
- [Fix: files are updated when done for sidebar tasks by devin-ai-integration - Pull Request #58 - nishio/ai_project_manager [https://github.com/](https://github.com/) nishio/ai_project_manager/pull/58]
- It's done.

[GitHub Actions CI for Server Tests by devin-ai-integration · Pull Request #57 · nishio/ai_project_manager](https://github.com/nishio/ai_project_manager/pull/57)
- They set up a CI.

We reflected on the week using what we've made so far.
    - [[Weekly journal 2025-03-01~2025-03-08]]
I would like the task description to be updated based on this kind of interaction, but currently there is no mechanism for that yet.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
List the tasks that should be added and the tasks that should be updated using the exchange so far.
Tasks to be added are `[{"title": ... , "description": ...} , ...] In a list of the form `.
Tasks to be updated are `[{"id": ... , "title": ... , "description": ...} , ...] In a list of the form `.
<img src='https://scrapbox.io/api/pages/nishio-en/o1 Pro/icon' alt='o1 Pro.icon' height="19.5"/>
Tasks to be added (new tasks)
json

```json
[
  {
    "title": "3/9 Preparation of materials for LT presentation", "title".
    "description": "Prepare presentation materials for the LT on 3/9. We will finish by the end of the week in the following order: skeleton, slides, and then brush up."
  },
  {
    "title": "Plurality Tokyo Namerakaigi's video editing and publishing", "title".
    "description": "The recorded data will be easily edited and published on YouTube or other media. It is preferable to work on this as soon as possible so as not to spoil the freshness of the presentation."
  },
  {
    "title": "Establishing a mechanism to allow Devin to do research", "title".
    "description": "Extend Devin and develop an environment that allows for automated paper research and experimental validation. Specific methods and operational policies will be discussed and prototyped."
  },
  {
    "title": "Let Gemini read Gmail", "title".
    "description": "To study and experiment with ways to import Gmail content into Gemini for summarization and automatic sorting. Authentication and security aspects will also be included."
  }
]
```

Tasks to be updated (update content and titles of existing tasks)
json

```json
[
  {
    "id": "T0107",
    "title": "Source code organization and README maintenance for public opinion map", "title".
    "description": "Now that Devin has gone private, we will organize the source code of the public opinion map and add a README so that it can be released as OSS. Cut out the parts that are not needed for public release and clearly state the license and usage."
  },
  {
    "id": "T0098",
    "title": "Notepad + night AI input flow validation (paper memo next morning start)", "title".
    description": "Trial operation of managing short-term tasks with paper memos during the day and inputting them collectively into AI at night. The next morning, tasks can be grasped by looking at the paper memo, and the AI is used for organization and supplementation. Measure effectiveness and consider improvement measures."
  },
  {
    "id": "T0116",
    "title": "Examine measures to deal with increased information channels", "title".
    "description": "Confusion is high with the increase of numerous information sources such as Signal, Slack, ChatGPT, etc. Start by identifying the major sources of confusion and try minimal integration and automation measures. Verify improvements while running a small operation."
  },
  {
    "id": "T0099",
    "title": "Developing task management scripts using o1 (local execution)", "title".
    "description": "Developed a task management script by replacing the API with o1 instead of ChatGPT 4.0. Run it in a local environment for now to avoid timeouts and other problems. Create MVP for basic functionality and check effectiveness."
  }
]
```


---
I created add_tasks.py and update_tasks.py and updated them respectively.
But humans, at times like this, wonder, "Did the AI's updated explanation erase anything important from the previous version?" and they get anxious.

So we need to make a review list of task additions and task updates, and a human needs to be able to look at it and "OK", "reject", or "rewrite by human" - right?

next  [[AI Task Management 2025-03-03]]

---
This page is auto-translated from [/nishio/AIタスク管理2025-02-27](https://scrapbox.io/nishio/AIタスク管理2025-02-27) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.