---
title: "Programming instructions issued to ChatGPT"
---

I didn't record this because it works most of the time, but I made a note of examples to share when people who don't do well ask me what I'm doing.
- Anything that doesn't say anything in particular means it worked without any problems.


---
[[git update-index --skip-worktree]]

---
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
There is data recorded in the following code
I want to display the "number of clusters" in chronological order for each conversation.
Write in Python.
<code>

(Remark) "The "code below" was Node.js, so the generated code was as well, Python was better, so I edited the prompt." The "code below" is just to hit the API and save it, so the schema of the JSON data is unknown, so it became a temporary code there.

---
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
Find access to the number of clusters.
<json>

<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>
As far as this JSON structure is concerned, information related to clusters is stored in the group-clusters key. This key is an array of objects with the cluster ID and its center coordinates, as well as a list of members in the cluster. The number of clusters can be obtained by counting the number of elements in this group-clusters.
<code>

---
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
Follow this code with code to print "the most clusters and the most recent data in each Conversation ID". Only the additional part should be displayed.

---
Fix bug due to difference in stringification of Date object between JavaScript and Python.
Original code
py

```
# Open the corresponding JSON file
filename = f"{conversation_id}-{max_cluster_record[0].strftime('%Y-%m-%dT%H-%M-%S.%fZ').replace(':', '-')}.json"
```


<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
`strftime('%Y-%m-%dT%H-%M-%S.%fZ')`
Z here is three digits.

<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>
Change as follows to allow display in milliseconds format.
py

```
# Format filename timestamps to 3-digit milliseconds
filename = f"{conversation_id}-{max_cluster_record[0].strftime('%Y-%m-%dT%H-%M-%S')}.{max_cluster_record[0].strftime('%f')[:3]}Z.json"
```



---
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
Create a corresponding dict of ID and human readable title based on the following material.
<document>


---
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>The matrix is a Pandas DataFrame with data for 592 users. We would like to visualize this in UMAP, and use the User ID later as it can be linked to other attribute information. Implementation.

---
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>There is a DataFrame named "data" with party data as PARTY in integer. The map with the party name is shown below, and I would like to represent this as a dot in Scatter.

(Supplemental) It seems that this instruction did not understand that "only valid items extracted from data are matrices, which must be mapped to each other", so it was necessary to rewrite the instruction separately.

---
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Regarding the matplotlib scatter, you can use the magnifying glass icon to narrow down the data and redraw it. Is it possible to add an event listener to display what that narrowed down range is?
<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>[https://chatgpt.com/share/6723a783-b0b4-8011-8c54-52ef24defc80](https://chatgpt.com/share/6723a783-b0b4-8011-8c54-52ef24defc80)

Convenient~~
---
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I would like to put the text on the legend, or if it is difficult to do so, I would like to put a patch to show the color.
<code>

----
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I want to expand and republish only `Selected range: x=[-14.85, -9.30], y=[6.60, 10.22]` of scatter that I already showed in matplotlib.
<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>(code to redo scatter)
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Is there any way to avoid redoing the SCATTER?

(It was there, but the scatter was displaying the text in the first place, so it needed to be redrawn.)

---
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Create 5000 100-dimensional vectors of +1 for, -1 against, and 0 missing values. The probabilities of +1 and -1 are equal, and the probability that there are less than 3 non-missing values is about 20%.

(Minor modifications to the formula were necessary.)
---
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Write a code that aggregates the number of vectors of the same value in the data, and then finds 10 of them in order of increasing number of vectors.

---
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Write Python code to receive the following jsonl and create a CSV of comment-id, comment-body

---
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Create a Python dict in a color suitable for displaying Japanese political parties in a graph.

---
This page is auto-translated from [/nishio/ChatGPTに出しているプログラミング指示](https://scrapbox.io/nishio/ChatGPTに出しているプログラミング指示) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.