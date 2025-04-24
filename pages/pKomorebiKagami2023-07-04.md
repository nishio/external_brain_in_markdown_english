---
title: "pKomorebiKagami2023-07-04"
---

prev [[pKomorebiKagami2023-07-03]]
I was able to update the poll.

I'll vote 100 votes.
- error unhandledRejection: error: new row for relation "votes" violates check constraint "votes_vote_value_check"
- Correctly rejected.

Voting results have been tabulated.

I think I'll let the RDB concentrate on keeping simple polling data, and let Firestore do the other UI stuff.
- For example, a structure with multiple questions in a topic should be placed in the Firestore, not in the RDB.
    - The original Polis "multiple questions in a topic, 1:N" relationship is where I have been feeling that there is not enough flexibility in the study so far.

Think Next Action
- Put topics and question list on Firestore
    - The list of questions now has to be sent one by one, which is a hassle, so we will make it possible to send multiple lines at once.
    - We'll do it to the point where everyone votes and the results are visualized.

We made it this far.
- ![image](https://scrapbox.io/files/64a3e80fce7767001b3dc44a.png)
- Let's first get whether the user has answered the question on the topic, and then, based on that data, hide the results if the user has not yet answered the question.
    - I'll get to that later.
    - No, I don't know what I voted for in the past when I revisit, so I still need to do it.
    - I can now retrieve my past votes and change the display.
        - It still looks terrible.
    - ![image](https://gyazo.com/57dfecfbeb2f9c1cbb83685052306059/thumb/1000)
Today's Summary
- You can now vote from the UI on your browser.
    - You can see your past votes.
    - Votes can be amended.
- The tally of votes per question now appears in a bar graph.

---
This page is auto-translated from [/nishio/pKomorebiKagami2023-07-04](https://scrapbox.io/nishio/pKomorebiKagami2023-07-04) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.