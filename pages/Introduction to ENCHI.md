---
title: "Introduction to ENCHI"
---

My mind is rather confused, so I'll first run one pomodoro and keep a record of it.
I don't know [[where is the appropriate place to write it]], so [[I'll write it here for now]].
    - [[🌀Where should I write?]]

🍅
Create a private repository
- omoikane-embed-enchi
- PRIVATE is the first case

push from omni
:

```
git remote add enchi https://github.com/nishio/omoikane-embed-enchi.git
git branch -M main
XXXX git push -u origin main
```

Oh, you're sending the LFS.
- Whether to rebase and erase
Oh, `git push -u origin main` is a mistake!
- `$ git push -u enchi main`
- Where is origin in the first place?

clone and open with new code
- `$ git clone https://github.com/nishio/omoikane-embed-enchi.git`
- `$ code omoikane-embed-enchi`

Run it locally for now.
- Copy `.env` from omni since it is not in the repository
    - PROJECT_NAME=enchi`.
- I do this with make_vecs_from_json.
py

```
payload = {
    "title": title,
    "project": PROJECT,
    "text": "\n".join(buf),
    "is_public": is_public,
}
```

    - `is_public=True` is hard coded.
        - I'll set it to false.
- Does having a separate `COLLECTION_NAME` in `.env` work?
    - Keep `COLLECTION_NAME` as `nishio`.
    - Ah, I have a feeling this will require traffic control in the future.
    - Is `is_public=False` for "I don't want the string hit by a vector search that is public"?
    - Uh, yeah, [[False dichotomy]].
        - I was thinking only two ways, "public" and "only you can see it," but now I'm thinking "public," "limited public," and "only you can see it," which is why Boolean is wrong in the first place.
            - [[Programmers are more likely to notice false dichotomies.]]
    - If you make `is_public=False` searchable in the future, and the generated information is entered into enchi, I can see a future where you accidentally enter information with `is_public=False` that should not be public to anyone but yourself, and it leaks.
    - Is `is_public=True or for_enchi=True` appropriate?
        - No, `is_public=True or project="enchi"`.
        - Why not just use `project="nishio" or project="enchi"` to begin with?
    - I wonder if my future self will make this decision properly...


🍅
:

```
prev_title, prev_lines = bot_output[-1]
                             ~~~~~~~~~~^^^^
IndexError: list index out of range
```

- This is due to the fact that the main branch is trying to get and read the latest notes, and since this is the first introduction, the latest notes do not exist
- I don't think we need the main branch in the first place this time, so I'll pass.

- Error due to private project
    - We just didn't support it yet.
    - done

I created one page with a manual trigger.
- Let's explore what form of activity would be best without suddenly making it automatic.
- Turn off periodic execution of Github Actions

Refactored.
- Let's see, what am I supposed to do with this by PUSHING it?
- Merge into omni...
    - Well, there's a complication with uncommitted diffs of the local version you're trying to make.
    - We need to organize the code over here.

🍅
> Where is origin in the first place?
- origin = core.
- source of confusion
- `% git remote rename origin core`
- `% git push omni main`
- `% git fetch enchi`
    - [[git fetch]]
- ![image](https://gyazo.com/e7fc85c1f4a0df1468bed850f8ca0499/thumb/1000)
- ![image](https://gyazo.com/359e241c3cb672ce5cadda058f9cff5e/thumb/1000)
- `% git push omni main`
- done!
git status

```
Your branch and 'enchi/main' have diverged,
and have 5 and 4 different commits each, respectively.
```

- That's right, what are you going to do?
- `% git branch -dr enchi/main`

Other
- Omoikane's bot was changed to "add your thoughts at the end of a random page".
- Bot on unnamed-projects was set to "suggest splits on the longest page".


---
This page is auto-translated from [/nishio/enchiへの導入](https://scrapbox.io/nishio/enchiへの導入) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.