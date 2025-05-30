---
title: "Human Task Scheduler Load Testing"
---

An attempt to clarify what needs to be corrected by putting a load on the [[scheduling]] mechanism of human [task
- see [Scheduling - Wikipedia](https://ja.wikipedia.org/wiki/%E3%82%B9%E3%82%B1%E3%82%B8%E3%83%A5%E3%83%BC%E3%83%AA%E3%83%B3%E3%82%B0)

[2015-11-21 Facebook](https://www.facebook.com/nishiohirokazu/posts/10207265168764043)
I've heard a lot of talk about how multitasking is less efficient than single-tasking, but unlike situations where there is a physical interruption such as a phone call, if there are multiple tasks running in parallel, simply switching tasks at your own timing is the same as single-tasking, and the performance should be the same. If you design your system with this in mind, you should be able to improve the performance, as if you were creating a micro-thread that you schedule yourself instead of creating a native thread for the OS.

So, when we increased the load to two to three times what it had been in the past with that design, it was interesting to see the patterns in the various things that were being taken out and what kind of things were being taken out.

...almost shirk the physical exam.
...I didn't apply for a day off work this weekend.
I have not worked on the workshop materials for 4 hours at all.
I haven't responded to your email about adding errata to the book (I remembered when I was writing the above).

The health checkup thing is a bug where you should check both the schedule and the task list, but you only look at the task list, start working on it, and forget about the schedule.

A bug that evaporates from the brain stack as a result of unnecessary procrastination without registering it in the task list, even though the application for working on a holiday should be submitted immediately when it is decided that it will be treated as working on a holiday. Maybe this case started with "I'll confirm if it will be treated as a holiday work," but in that case, the "confirm the result and act" task should be piled up in the schedule after an appropriate time when waiting for someone else's IO.

Workshop material preparation is a typical bad task. The first step is not clear, the goal is not clear, the deadline is not clear, the requirement level is not clear, etc. As a first step, the task is loaded with "1 Pomodoro note about workshop materials," and left unattended. When I decided to do it, I thought "Oh, I have to refer to that document" and didn't do it, but I didn't revise the task there.

It is not a proper inbox when there is more than one screen of data in the inbox.

You can't execute the errata email or the task if you don't have the book with you! And you can't execute the task until Tuesday because the book is at the office now!

Errata email 3 days old and it's been in my email inbox for a long time and I haven't dealt with it!

I had a notebook in my Evernote called "inbox" and a notebook called "today's tasks" and a notebook called "this week's tasks" and that worked fine when the majority of the tasks were R&D. However, when there were more IOs waiting for others, a lot of modifications became necessary.
First of all, if you erase a task at the point when "your task is finished (you handed the ball to the other party)," you will forget about it as it is when the ball is not returned from the other party.
If you pile them up as a task of "wait for the response and do the work," it's fine when the number is small, as it has been, but when the number increases, the habit of "skimming and skipping" occurs, and you still forget.
So I decided to load it up in the form of a task called "Prompt if not - on Thursday". This is the premise of what I am going to write so far.

So, even though I was not aware of it, many "things to do at specific times (small schedules)" have appeared here in addition to "things I perform" in the "tasks". What happened as a result of not being aware of this change in data content?
I thought it was wrong to write such a detailed schedule in my notebook because there is a lot of it and it is characterized as "if I get a reply right away, I will do it without waiting for the due date". I forgot to look at "Today's Tasks".

The question is, in the first place, was it necessary to separate them into separate notebooks on Evernote?

Evernote, moving information between notes is not easy. Opening a note in a separate window and cutting and pasting is not convenient, and I can't do it on my iPhone. If you want to separate and organize your notes, it needs to be easy to move them around.
If we try to achieve this in Evernote, we could make one task into one notebook and realize it by moving notebooks around, but it seems like we are splitting a disposable chopstick with a hatchet.
The other method is to write everything in one notebook. I have some concerns about too much information and not having too much warbling, but this one seems to be better.

---
This page is auto-translated from [/nishio/人間タスクスケジューラの負荷試験](https://scrapbox.io/nishio/人間タスクスケジューラの負荷試験) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.