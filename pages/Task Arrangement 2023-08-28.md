---
title: "Task Arrangement 2023-08-28"
---

# Re4: ver.1
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>What about Next Action?
<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>Understood. Based on the information provided, the Next Action is as follows
- Book Conversion:
    - Evaluate existing book conversion scripts to see if they meet your requirements.
    - Implement your own scripts or modify existing scripts as needed.
- Copyright measures:
    - Sample C2 output and identify possible copyright infringement risks.
    - Plan and implement a human review process for AI outputs.
    - I was thinking about avoiding it because it's a pain in the ass, but now that I think about it, it might be an option.<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
        - We can generate it first in a private project between just me and AI, and then move the ones I see and think look OK.
        - You can also post the "reference section" on the page in that private project, because it's private.
        - If you look at the content of the page and I decide that it's OK because it's not similar, then you can flag it.
            - If you determine that it's NG, it would be nice to be able to state that too.
            - If you decide that a little editing is OK, you can edit it.
- Use of "The Engineer's Art of Intellectual Production."
    - Plan how to map to related content in Scrapbox.
        - I'll try a few things on the command line first.<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
    - Develop a strategy for utilizing the English translation of "The Engineer's Guide to Intellectual Production."
- Data migration to Qdrant:
    - Define procedures for data migration to Qdrant and perform test migration.
    - Prepare countermeasures in case of failures or problems.
- Incremental Reading implementation:
    - Define the details of the update algorithm.
    - Plan and implement updates to the system based on the algorithm.
- Qualia-san Directions:
    - Schedule a meeting to establish specific goals and target markets for the project.
- Omoikane novel generation:
    - Begin designing an algorithm to randomly select themes and sources of inspiration for the novel.
    - Perform an initial test of AI generation and evaluate the results.
- Quality Assessment:
    - Investigate frameworks and methodologies for setting quality metrics for novels.
    - Conduct initial quality assessment tests and adjust AI settings and algorithms based on the feedback.

It is recommended that tasks be sequenced based on these Next Actions. It is important to reevaluate the priorities and content of actions as new information and issues become apparent during the progression.

The order of execution is a freebie.<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
- That's because you didn't explain the dependencies of the tasks.
- I guess the first step is to try the Qdrant migration using "The Intellectual Production of Engineers" which has already been converted from a book...
- ![image](https://gyazo.com/fd8726843b236510acdf1399b8cac07e/thumb/1000)
- No, it's Incremental Reading.
    - Why is it that when I organize in Kozaneba it's obvious, but when I'm thinking in writing, my priorities get out of order?
    - Is it a phenomenon in which tasks that have already been sufficiently verbalized are prioritized over tasks that have not yet been verbalized?

# Kozaneba

![image](https://gyazo.com/3107fe1e139ee1f7e979068b0d990c7c/thumb/1000)
![image](https://gyazo.com/0ecbf745bce45228d82fd2d3aa6baf53/thumb/1000)

![image](https://gyazo.com/900cf0c2b708f197a6428a9e9334f556/thumb/1000)

# Re3: ver. 1
<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>
Based on the responses, the following recommendations and next action steps are suggested

Regarding the AI reading Scrapbox system:
- Book Conversion: Before using a script from an external source, it is necessary to check what format and functionality the script has. Also, make sure it can be applied to either Project Gutenberg or cut-and-scan PDF. If you are implementing it yourself, it may be better to use an existing script as a reference while adding the necessary functionality.
- Copyright handling: To minimize copyright risk with respect to C2, it would be a good idea to have a process for human review of the AI's output.
- Use of "The Engineer's Guide to Intellectual Production": Based on this book, mapping with related content in Scrapbox and measures to utilize the English translation should be clearly formulated.

Regarding search:
- Data Migration: Find out in advance the process and possible obstacles in migrating existing data to Qdrant.

Regarding page creation style:
- Application of Incremental Reading: The algorithm for updating should be defined and the design of the system should be based on it.

Regarding Qualia-san:
- Project Direction: Clearly define your goals and target market, and adjust your project direction accordingly.

Regarding Omoikane:
- Novel generation: an algorithm should be designed to randomly select themes and sources of inspiration for the novels to be generated.
- Assessing quality: considering means to assess the quality of the generated novels and establishing a feedback loop would be expected to improve the quality of the AI's output.

Based on these recommendations and steps, it is effective to clearly define and plan each task.


# Re2: ver. 1
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>

Regarding the AI reading Scrapbox system:
- Is the ability to read books a new development or an extension of an existing feature?
    - No additional development is required for "The Intellectual Production of Engineers" since it is already in Scrapbox JSON format.
    - For other books, it is necessary to convert books to Scrapbox format, and there are scripts related to this if you look for them, but it is undecided whether it is better to use them or to implement them yourself
        - The process is a little different depending on whether the book is from Project Gutenberg or a cut and scanned PDF.
- How much weight should be given to copyright concerns?
    - As for everything else except C2, no problem at all.
    - As for C2, the question is whether "what AI wrote after reading the work" is within the scope of rights of the copyright holder of the original work.
        - I'm relying on it, so if it's similar, no.
        - I'm sure we can control the prompts to avoid similarities, but it's hard to guarantee 100%.
- What are the specific expected outcomes of reading The Intellectual Production of Engineers?
    - It would be nice if AI understood the "intellectual production techniques of engineers" and could advise on specific human situations and further develop the content.
    - Nishio's Scrapbox has a large amount of content related to the intellectual production techniques of engineers, but it does not correspond to the content of the book.
    - An English translation of the Engineer's Guide to Intellectual Production has been published, but I don't see a way to make use of it, and I'd like to see some development.
- Regarding the acquisition of content from Project Gutenberg, Aozora Bunko, etc., do you have a specific target literature or genre in mind?
    - One case has already been decided and is being prepared for experimentation.
    - I can think of a few cases.
- For private projects, what are your thoughts on the scope and permissions of the user groups to be shared?
    - There are two ways.
        - Deploying to a private project that already exists and is no longer in motion in a way that users there might be interested in.
        - Start with just me and AI on an empty project.

Regarding switching the search from local Pickle to Qdrant:
- What was the background and advantages of choosing Qdrant?
    - Easy, already working.
- Need to migrate existing data?
    - Book data is not yet included and needs to be included.

Regarding page creation style:
- If we adopt the overwrite mode, how will the existing data be backed up and how will the history be managed?
    - Overwrite mode is "append on top" so all history remains.
- If you were to implement the Incremental Reading methodology, what specific workflow changes would you make and what are the expected benefits?
    - Do not update for all targets
    - New arrivals are top priority
    - Then prioritize using the time since the "last human update"
    - What kind of algorithm should it be?
        - If the last update is human, the more time that has passed, the higher the priority?
        - If the last update is AI, it will not be updated until 6 days have passed.
            - If you renew after 6 days, the next one will be after 9 days (1.5x)

Regarding Qualia-san:
- What are the goals and expected outcomes of this project?
    - Not very clear.
    - It is also unclear whether it aims to be popular in Japanese-speaking countries or English-speaking countries.
    - One option is to input in Japanese and aim for recognition in English-speaking countries.
- Do you already have a specific requirement or image in mind regarding the design of the virtual character?
    - be (usu. of inanimate objects)

Regarding Omoikane:
- Is the genre or theme of one novel per day fixed or does it fluctuate?
    - Fixing it to be near-future science fiction, but randomly reading existing pages for inspiration.
- Is there a quality assessment or feedback mechanism considered for the generated novels?
    - No, sir.

Answering these questions will help us better define how to proceed and prioritize each task.


# Re: ver.1
prompt

```
You have an engineering task management role. Please review the notes below and ask any questions you feel are necessary to determine what to do next
### ...
```


<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>In order to understand the details of the task and to determine the direction of progress and priorities, the following questions were considered

Regarding the AI reading Scrapbox system:
- Is the ability to read books a new development or an extension of an existing feature?
- How much weight should be given to copyright concerns?
- What are the specific expected outcomes of reading The Intellectual Production of Engineers?
- Regarding the acquisition of content from Project Gutenberg, Aozora Bunko, etc., do you have a specific target literature or genre in mind?
- For private projects, what are your thoughts on the scope and permissions of the user groups to be shared?

Regarding switching the search from local Pickle to Qdrant:
- What was the background and advantages of choosing Qdrant?
- Need to migrate existing data?

Regarding page creation style:
- If we adopt the overwrite mode, how will the existing data be backed up and how will the history be managed?
- If you were to implement the Incremental Reading methodology, what specific workflow changes would you make and what are the expected benefits?

Regarding Qualia-san:
- What are the goals and expected outcomes of this project?
- Do you already have a specific requirement or image in mind regarding the design of the virtual character?

Regarding Omoikane:
- Is the genre or theme of one novel per day fixed or does it fluctuate?
- Is there a quality assessment or feedback mechanism considered for the generated novels?
- Answering these questions will help us better define how to proceed and prioritize each task.


# ver.1
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
AI reads Scrapbox system
- Very useful
    - I want to include books in my reading list.
        - There are concerns about AI reading books copyrighted by others and writing directly to the public project.
        - A: Read about the intellectual production techniques of engineers.
            - It doesn't matter because the author is me.
        - B: Use copyrighted materials such as Project Gutenberg or Aozora Bunko
        - C: Make the project private
            - C1: Make it a private, personal project
            - C2: Make it a multi-person private project
                - There is a project on intellectual production techniques for engineers.

- Make searches come from Qdrant instead of from local Pickle

- We feel that the style of continuing to use one page (overwrite mode) is preferable to the style of creating one new page per day (main branch)
    - But easily becomes too many updates.
    - Right now, I'm randomly selecting 10 cases from the list of renewal targets.
        - Incremental Reading techniques could be used.

Qualia-san
- Style of generating and answering questions and extending them as a page
- Virtual character design

good-natured old man
- AI writes one novel a day.

---
This page is auto-translated from [/nishio/タスク整理2023-08-28](https://scrapbox.io/nishio/タスク整理2023-08-28) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.