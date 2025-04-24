---
title: "Muscle training memo in Notion"
---

2022-01-17 Done.
- Enter the day's workout from your phone without having to manually enter the name of the workout or the date
- Each workout can have a free description of any length

---

- Can't I just delete the title field from the record?
    - looking like one is not going to make it
    - [https://www.reddit.com/r/Notion/comments/hadrpu/a_table_without_a_title_column/](https://www.reddit.com/r/Notion/comments/hadrpu/a_table_without_a_title_column/)
- Is it possible to hide the title field in the calendar view?

hmm
So the base class for all information is "page" and it has a "title" field.
- Subtle

![image](https://gyazo.com/c36d413a63979421aa06ac1d1ba60454/thumb/1000)
![image](https://gyazo.com/c81a225dc440dc2c4f22784d8a7855c9/thumb/1000)
- Subtle

![image](https://gyazo.com/6ca9d43b06c88dbd1db389670add20b0/thumb/1000)

hmm
For example, should I make a separate page for each muscle training content and write the content on a single line in the title? But that would be a pain in the ass to make it a separate record," he said, and he wouldn't do it.

Wouldn't it be better to use kintone instead of Notion?
![image](https://gyazo.com/9b19e16615bf303106ab4990914912b8/thumb/1000)
![image](https://gyazo.com/4ae4f34f46eb6a681980bd7cb0597499/thumb/1000)

Can't the multi-select be the target of the calendar view...
- Record ID is displayed because the title is not specified.
- It is possible to change the look and feel with JS customization...



If I make a lot of messy notions in Notion for the sake of "being able to display on the calendar", it will be too much of a hassle to write muscle training notes, and I'll stop doing muscle training.

I tried to do it in Notion because I was worried that "doing it in Scrapbox might destroy or slow down the existing network" due to Scrapbox's poor squeeze, but maybe what I really need to do is to do it as a separate project in Scrapbox.

![image](https://gyazo.com/4dfa675f4f390ac57d56a9d373ab0170/thumb/1000)
![image](https://gyazo.com/15fd63427bd1412edd70390ebee25c4f/thumb/1000)
I have a feeling this is the way to go...
- Yes, it's not a calendar view, but "Is it really an important requirement that it be a calendar view?" but "Is it really important that it be a calendar view?

What are the really important requirements?
- To be able to note when you have done muscle training without stress.
- Easy to look back (what is)
- Need to be able to take notes easily.
    - I may take notes in the park on my phone; I don't require a PC.
    - Need less work to do when you decide to take notes.

My wife sent me the video.
[https://www.youtube.com/watch?v=ZQ-uUtHHyzc&feature=youtu.be](https://www.youtube.com/watch?v=ZQ-uUtHHyzc&feature=youtu.be)
Ah, I see. I tried the template button and thought, "No, not even if text is added..." but you can shove a record in there.

I made it.
- ![image](https://gyazo.com/fcaf1de8e87f055315ce14a0aea97cf6/thumb/1000)

Drag and drop to calendar view is not available on smartphones.
To insert a date and time using a method other than dragging to the calendar view
- Proposal to change the date and time used to display the calendar view to the date and time of creation.
    - You can't edit it later, so you're obligated to make sure you create a record on the day you muscle up, but if you do that, no problem.
    - No, no, I won't be able to put in the data from the muscle training before yesterday.
- Add undated records at the park and put them in the appropriate places in the calendar view when you return.
- Q: If I use "@today" for Date, won't today's date be included when it is generated?
    - A:Date type is INVALID because it is not text.

The "record title contains a specific string" can be narrowed down, so it is easy to look back in the past if each narrowing is generated
![image](https://gyazo.com/7cdb505e6b5bbfcd06781fe599edb415/thumb/1000)
I'm starting to feel like I can do it, but it's becoming more and more of a hassle.

PS
- My wife suggested that we could do it with Linked Database.
- If you use Linked Database to create a database called "Today's" or "Title contains barhang", you can create a record with those values automatically inserted by simply pressing the Add button.
- I confirmed that it works fine on my phone because it doesn't require any dragging, etc. against the addition.

So let's make it again from scratch.
First, create an empty page.
![image](https://gyazo.com/6df60c4b352049bb96661a7eaab840db/thumb/1000)
And create a database.
![image](https://gyazo.com/0773c2091f5c7f687c7dbd1749689937/thumb/1000)

Creating a Linked Database
![image](https://gyazo.com/541fca1871f77454c18543e2faa9e48e/thumb/1000)
Today in Filter
![image](https://gyazo.com/63313783ea4de2f140fbcadc5a278789/thumb/1000)
Duplicate and add Filter
![image](https://gyazo.com/b50a33497d7ce50f50ddb5d6cd4466ab/thumb/1000)
Assigned to days of the week using Linked Database for all types of workouts
It's done.
![image](https://gyazo.com/cc7c4810d7891f1e09cf62435ce7044b/thumb/1000)
If the data entry part goes smoothly, the history part can be done later.

2022-01-17
Strength training is twice a week, so I don't get much data in, maybe I should record stretches with it.

[https://twitter.com/mizukih__/status/1481944275860750340?s=21](https://twitter.com/mizukih__/status/1481944275860750340?s=21)
I can see the record before and after right away, so I can see "how many times I did squats the last time I squatted" right away.

![image](https://gyazo.com/bd68ebac742b1596332a749fad4e46fd/thumb/1000)
- As for changing the title of the first entry, you don't have to create a separate Linked Database, you can use a template.
    - I wonder if there is a way to set the initial value of the date in the template to "today"...
- Huh? No.
    - In the template, there's a value in the title, but it disappears when you create a record.
    - They've been saying that for two years.
        - [https://www.reddit.com/r/Notion/comments/e5ih9g/automatically_insert_a_title_for_pages_opened/](https://www.reddit.com/r/Notion/comments/e5ih9g/automatically_insert_a_title_for_pages_opened/)

Fairly essential differences between Notion and Scrapbox
- Notion can be the same string of record titles.
- Scrapbox tries to summarize the page titles if they are the same string.
As a wiki, it's natural to summarize, and as a database, it's natural not to summarize.


2022-01-18
- ![image](https://gyazo.com/6e759c128710cf4cdc098710ac3ce971/thumb/1000)![image](https://gyazo.com/ad49890520afee989d5433ea7248a4fe/thumb/1000)
- Input from the phone is not a hindrance, but the display hides the crucial number of exercises.
    - The width of the phone is too narrow.
- The year cannot be removed by changing the date format.
- The display column for the date itself was moved to the right.
    - ![image](https://gyazo.com/9dce20c5713a2257e5ec3fd511867d2f/thumb/1000)

Gallery view for looking back
- ![image](https://gyazo.com/76e4c8d7ebcd0cdab366285df2d6fa26/thumb/1000)

---
This page is auto-translated from [/nishio/Notionで筋トレメモ](https://scrapbox.io/nishio/Notionで筋トレメモ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.