---
title: "pVectorSearch2023-06-13"
---

from  [[Diary 2023-06-13]]
prev [[pVectorSearch2023-06-07]]

[[Make private materials eligible for vector search]].
- I have a feeling we're going to have an accident.
- First, put the public flag on the data created from the public Scrapbox.
    - And make the default search from public
    - If you're going to re-install this data, why not re-crawl it first, even if you don't add the UPDATE feature in its current state?
- private is diverse, so make it a separate tag instead of a private flag
- Display a check box to add records with a specific tag to the search target list only for people with specific permissions.

Add search targets for specific people only
- Working on authorizing certain people, I want to make it an in-byte code because it would be a mistake for me to work on it.
- The implementation of this feature is going to be buggy to begin with.

Notion seems to be able to export entire subpages in Markdown.
- ![image](https://gyazo.com/b7524c5f56157b4ba95ae507441b5577/thumb/1000)


> If you're going to re-install this data, why not just re-crawl it first, even if you haven't added the UPDATE feature to the current situation?
- ✅Recrawl all together, about 5 minutes.
embedding from JSON was not yet batch.
- Single ✅ code
Experiment with filtering the search during embedding town
- I know how to call the API.
- We need to receive data about the filter from the UI.

Talk about making Notion a search target.
- I'd like to see you jump to the target when you click on a hit.
- But unlike Scrapbox, the link destination is not determined by the project and page name.
- We need to come up with data for the UI.
- This time, a particular private page is exported, including supppages.
- If I had the URL of the root page, could I restore it?
    - Oh, I see.
        - local filename
            - `Proposal 2: Nishio 7d7c95ceaeb446418bffe462034292bd.md`.
        - This part of the ID looks like a worldwide unique ID.
            - You can jump to the destination page with `notion.so/7d7c95ceaeb446418bffe462034292bd`.
    - Then `{type: notion, id: xxx}`...

:

```
processing 15469 pages
100%|...| 15469/15469 [00:53<00:00, 290.87it/s]
processing 13893 tasks in 277 batches)
100%|...| 278/278 [11:27<00:00,  2.47s/it]
```


Well, if I understand it correctly, this is an implementation that can easily be used for differential updates.
- Past self, great!

:

```
# halsk
processing 1281 pages
100%|...| 1281/1281 [00:02<00:00, 619.70it/s]
total tasks: 2221,  1.00% was cached
processing 0 tasks in 0 batches)
0it [00:00, ?it/s]

# yuiseki
processing 2778 pages
100%|...| 2778/2778 [00:09<00:00, 289.72it/s]
total tasks: 4738,  0.92% was cached
processing 375 tasks in 8 batches)
100%|...| 8/8 [00:25<00:00,  3.13s/it]

# tkgshn
processing 5750 pages
100%|...| 5750/5750 [00:11<00:00, 486.96it/s]
total tasks: 12117,  0.97% was cached
processing 308 tasks in 7 batches)
100%|...| 7/7 [00:20<00:00,  2.89s/it]
```


I was able to update the diff.

I was able to get the code to take the title and ID for each page from the Notion export data.

The rest will be done tomorrow.
TODO
- Creating Data from Notion
- Create a view of Notion search results
- Only people with certain privileges get the UI out.
- Search filtering by checking specific permissions
- Receive data about filters from the UI
- Re-enter data into Qdrant.

2023-06-14
- I thought it would be better to include Discord discussions in the search, so for now, I've decided to split the logs by date and put them on Notion this time.
    - Abst of various papers were put into Notion at DeepL
    - Early minutes from Google Docs were also copied and pasted into Notion.

Create data from ✅Notion
- Try it in Local's qdrant.
    - ✅Confirmation that it is a hit if it is left as is.
    - Confirm that if you are searching from ✅public only, you will not get any hits.
✅Create a view of the Notion search results
- You can now click on a search result to jump to either Scrapbox or Notion.

Only people with certain privileges get the UI out.
- Hmmm, what a pain in the ass.
- For example, if you reverse-engineer the JS to make the display condition that a specific key is in localStorage, you can do it.
- Should I check my login status even if it's a hassle?
- Consult with GPT4: [[Feature Toggle]] under [[Custom Claims]] in [Firebase Auth
    - [https://chat.openai.com/share/d4be9a75-1e8a-4a3a-b3fe-effaa1efc200](https://chat.openai.com/share/d4be9a75-1e8a-4a3a-b3fe-effaa1efc200)
    - Ah, I see, we can create an API to grant and do it on the server side.
    - [Add Firebase Admin SDK to your server](https://firebase.google.com/docs/admin/setup?hl=ja)
    - The GPT4 information was a bit out of date and the line break escapes were no longer needed.
        - These skills are still needed.
    - I was able to display it.
- ![image](https://gyazo.com/d5a812c16b793709c754b33de850cff4/thumb/1000)![image](https://gyazo.com/3b8e53257a7bd9bd965c970a213faaee/thumb/1000)
    - It's done.

Search filtering by checking specific permissions
- When featureA is ON, that information is also passed to the search API. Then, after confirming that the user is authorized, the search is reflected in the filter settings.
- No, this is a different issue, being able to switch the search target with a checkbox and allowing only those with special privileges to search for special targets.
- Let's just do the latter first because it's too complicated to do all at once.
- It's done.

The only thing left to do is to find a way to make it possible to give Custom Claims to specific users without me having to mess with the DB.
- Take password with prompt and send it to setCustomClaim API
- Why was I able to set it up last time but not this time?
- > When a user's new claim is changed in the Admin SDK, it is propagated to the authenticated user on the client side by an identity token as follows
- >  The user logs in or re-authenticates after a custom claim change. The resulting identity token issued will contain the latest claim.
- >  When an old token expires, its identity token is renewed in the existing user session.
- >  The identity token is forced to be updated by calling currentUser.getIdToken(true).
    - [Controlling Access with Custom Claims and Security Rules | Firebase Authentication](https://firebase.google.com/docs/auth/admin/custom-claims?hl=ja)
- Ah, I see, it's cached.
- UI aside, it's done.
- Custom claims should be added, but now they're being overwritten, which is good because we only have one right now, but we need to fix it when we do the second one.

![image](https://gyazo.com/1af1f02dd048cee348904a7d6e21973a/thumb/1000)
- ![image](https://gyazo.com/2497a73d671c1780bfe6ea10fb0e97b9/thumb/1000)

Send data to the cloud side
- All replaced this time.
- The write operation timed out` even if I put in code to stop indexing and wait 1 second for each batch insert.
- I changed the code to wait 10 seconds and retry when it fails.
- ![image](https://gyazo.com/799c5be1d5ab2697891a269a0051f714/thumb/1000)
    - Wow, three bumps in the road at the beginning, but the rest is pretty steady.
    - If so, then the current design, which only sleeps more when it falls, instead of sleeping every time, seems to be correct.

The problem gets worse on iPhone, I figured out how to reproduce it on PC.
- ![image](https://gyazo.com/73df1b8399016a56ed7d0a35b4b1257c/thumb/1000)![image](https://gyazo.com/478aafb16a5535e199fa1f307b4d43d8/thumb/1000)
- Fixed.

Deploying to Vercel environment is rubbish.
- Forgot to set environment variables
    - Why don't we just do the Vercel side when we change the .env.local?
- There was a path that did not pass through Firebase initialization.
    - careless mistake

It worked, and we're happy.

---
This page is auto-translated from [/nishio/pVectorSearch2023-06-13](https://scrapbox.io/nishio/pVectorSearch2023-06-13) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.