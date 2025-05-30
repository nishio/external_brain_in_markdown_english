---
title: "Communication regarding scheduling"
---

Interesting analysis [https://www.facebook.com/mizukitanno/posts/10155901191498796](https://www.facebook.com/mizukitanno/posts/10155901191498796) of the [[pain point]] of the task of "scheduling a meeting."

My own organization
- There are cases where you want to communicate to meeting participants
    - Example
        - Change of Schedule
        - Agenda Sharing
        - Sharing of Minutes
- Pain occurs when calendar and communication tools are not integrated.
    - Example: Google Calendar for calendar, Slack for communication
    - Check the calendar tool to see who is participating in the meeting
    - Create a group chat with all its participants on the communication tool side.
        - In Slack, an unnamed communication group can be created by specifying multiple people to DM
            - No way to check if it is already there.
            - The good thing is that they can be created without the cost of naming them, but as the number increases, they become unidentifiable without a name.
                - Naming it will cost the same as the cost of human retrieval.
            - Human conversion costs when personal IDs on the calendar do not match personal IDs in Slack
    - The results of communication on the group chat need to be written back by a human on the calendar tool side.
- When calendar and communication tools are integrated
    - Example: Cybozu Garoon
        - Register meeting schedules in a calendar tool → create a bulletin board-like structure → communication is done there
        - It can be said that a communication group is created with the name of the appointment at the appointment registration stage.
        - There are downsides, of course.
            - Separate forums for each event, so that if the same members repeatedly hold meetings, each discussion is divided into different forums.
            - Since there is a permalink on the previous event (and its board), put that link on the new event's board [[Avoidance by operation]].

remarks
- Interesting that after reading the speaker's post, two people misunderstood that finding free time is a pain point.
    - Easier to notice the pane if the person has experienced a state with function and then moved to a state without, but harder to notice if the person is in a state without it from the beginning.

- Since the root of the problem is that the calendar tool does not have a communication function, it would be a good idea to add a comment box.
    - Reminds me of LUNARR trying to put a communication feature on every page.
        - Services with too high a level of abstraction have high learning costs.

- Proposal to have notifications sent in a non-email manner.
    - I wonder if API standardization should happen since different people have different convenient notification front-ends.

#Groupware
---
This page is auto-translated from [/nishio/日程調整に関するコミュニケーション](https://scrapbox.io/nishio/日程調整に関するコミュニケーション) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.