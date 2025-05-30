---
title: "Experiment with changing the sort order in Scrapbox"
---

- Scrapbox is a dialogue with your past self
- Scrapbox is a timeless tool
- Written 160 days ago: [[passage of time]].

- And yet they are usually displayed in "updated order"!
- I only have myself these days!
- I want to have a dialogue with myself a long time ago!

Two types of functions were implemented.
- Past This Day Features
- Interval Iterative Method Function

Past This Day Features
- Ability to display "pages updated n years ago
    - [[This Day in the Past" on Facebook]] feature
    - This is a feature that shows posts from n years ago
- But a year ago, we weren't utilizing Scrapbox yet, so it didn't look interesting.
    - ![image](https://gyazo.com/f2f691defff4465c7dfc5a9bc24e00dd/thumb/1000)
- Maybe if you make it "100 days" instead of "a year," more people might enjoy it.

Interval Iterative Method Function
    - A [[step-by-step procedure]] is an algorithm often used for learning word cards, etc.
    - Correctly answered cards are presented at progressively longer intervals
    - The author of the interval repetition method app SuperMemo suggests [Incremental Reading
        - Put the text you intend to read in your system, and when you read it, pull out the important parts.
        - Sentences are presented at progressively longer intervals; excerpts start at shorter intervals.
        - The ones I thought about reading but didn't really get into are slowly sinking in with longer presentation intervals.
        - Good for "[[read afterwards]]"
- My implementation this time
    - Present articles that are more than 10 days old from the last update date at progressively longer intervals: 10, 20, 40, 80, 160, 320...
    - "Well, what's this page called 'History' that hasn't been updated in 320 days?" I'll be like...
    - If you don't update, your rankings will drop, and if you do, the next time you update, you'll be out in 10 days.
    - ![image](https://gyazo.com/3bbcd7d6cdae1d6c3d9bf169a79f4366/thumb/1000)
    - The 322nd one is down to 9th place.
        - It's down to about the same position for 161 days.
        - The newer it is, the speedier it goes down.
        - The 20-day one is way down because 4 days over against 320 days is equivalent to 6 hours against 20 days.
- use case
    - For a project like mine that is just a bunch of stuff, you can use it and look at it and say, "Oh, I used to write this kind of stuff.
    - If the page seems to have questions and answers, review them when they appear, and if you solve them correctly, do nothing, and if you don't, add to them, you're more likely to get them right often.
        - The current system does not have a mechanism to mark "correct answers" and prevent them from appearing tomorrow.
        - It's like skipping over, "This was done yesterday."
    - Clip more and more "web pages to read later" or "e-books I've bought," and they'll pop up from time to time.
    - I'll put in a "I'll do it someday."

- I wanted to use it on my iPad, so I made it a web service instead of a Chrome extension.
    - [https://nishio.github.io/scb_sort/](https://nishio.github.io/scb_sort/)
    - But Safari on iOS can't copy the entire selection of API responses.
    - The following bookmarklet will allow you to select all
        - javascript:document.body.contentEditable=true;
- They ported it to UserScript [/customize/"this day in the past" function](https://scrapbox.io/customize/"this day in the past" function).
    - No need to copy and paste JSON
    - However, it is not suitable for my use case because "only a little is shown," "selecting one makes the list disappear, so you have to click the button again to see the next one," and "each button click takes about 3 seconds.
    - It fits my use case, but "I can't see other people's projects" is also a problem?

-----
- 2018-05-23
        - [[This Day in the Past" on Facebook]] feature
        - Show creation date n years ago
        - Can you get a list of pages with dates and times?

    - [[Incremental Reading]] / [[Incremental Writing]]
            - [[How to Achieve Incremental Reading with Scrapbox]]
            - You think too much about details.
        - As a first step, you can simply "show f(n) days from the update date".
            - Trying to use the last access date as the starting point makes it necessary to have display interval data.
            - As long as there are no updates, the display interval will grow at a constant rate, so just expand it.
        - Cloze Deletion is not made first because it is not clear if it is needed in the first place.

    - I don't know how to deal with `No 'Access-Control-Allow-Origin' header is present on the requested resource.`, so I'm saving the JSON locally for now.
        - As soon as I figure out how to hit Scrapbox's API from a different domain, I'll publish it on the web...
            - They say there is no way.
            - Hands to do with Chrome Extension
            - Is it an iframe because I want to see it on my iPad?

#Scrapbox Customization


---
This page is auto-translated from [/nishio/Scrapboxのソート順序を変える実験](https://scrapbox.io/nishio/Scrapboxのソート順序を変える実験) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.