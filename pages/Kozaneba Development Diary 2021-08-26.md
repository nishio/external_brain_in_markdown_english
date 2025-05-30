---
title: "Kozaneba Development Diary 2021-08-26"
---

prev  [[Kozaneba Development Diary 2021-08-25]]
![image](https://gyazo.com/9375715516dbb7ae01077f30f78b2294/thumb/1000)



---
Ba list sorted by date and time
- A composite index will be needed.
- ![image](https://gyazo.com/de456b6ccd9ec0208cd43823b3ad2a10/thumb/1000)

Talk about testing with an emulator and being easy.
[https://techlife.cookpad.com/entry/2018/11/05/143000](https://techlife.cookpad.com/entry/2018/11/05/143000)

Change Firestore rules to allow read-only sharing

NG, syntax check is fine, but the tutorial test is mocked up by retrieving the past Ba list.
firestore rules

```
service cloud.firestore {
  match /databases/ba/documents {
    function is_writer() {
      return request.auth.uid in resource.data.writers;
    }
    match /{document=**} {
      allow create: if true;
      allow update, delete: if resource.data.anyone_writable || is_writer();
      allow get: if true;
      allow list: if is_writer();
    }
  }
}
```


My understanding of the path was wrong.
- Not `/databases/FOO/documents`.
- It was `/databases/{database}/documents/FOO/{document}`.

> match /databases/{database}/documents declaration specifies that the rule should match the Cloud Firestore database in the project. Currently, each project has only one database named (default).
- [Structuring Cloud Firestore Security Rules | Firebase](https://firebase.google.com/docs/firestore/security/rules-structure?hl=ja)
- I see that the `database' is the `default'.

OK
rules

```
rules_version = '2';

service cloud.firestore {
  match /databases/{database}/documents {
    match /ba/{document=*} {
      function is_writer() {
        return request.auth.uid in resource.data.writers;
      }
      allow create: if true;
      allow update, delete: if resource.data.anyone_writable || is_writer();
      allow get: if true;
      allow list: if is_writer();
    }
  }
}
```


Modified firestore rules to allow read-only sharing.
- Without the emulator, it would have been a lot of trial and error.
- Emulators allow trial and error at hand without waiting for rule updates in the production environment.
- ![image](https://gyazo.com/ae804631871deb49cfa1942cfa0f920c/thumb/1000)

Right now, the only control for a place is "change title," but when we start doing more things, there should be a dialog for the place.
- Change of title
- read-only sharing
    - By default, if you know the URL, you can edit it.
    - Change the URL so that it cannot be edited even if you know it.
- Make a copy
- deletion

Create New
- Maybe open /#new in a new tab from the user dialog?
- ✅

Something's still not right.
- Displacement when putting an empty group in an empty group?
- It is misaligned when you put an empty group in an empty group and put kozane in that group.
- Should the "empty group" survive or disappear in the first place?

`kozaneba.constants.group_padding = 5; kozaneba.redraw();`
before
![image](https://gyazo.com/83288e5799e0c164a43124208d650a1f/thumb/1000)
after
![image](https://gyazo.com/97db16e56e6e7c6d7020b7ead8e75044/thumb/1000)

When I try to organize a study session document that has already been written to some extent, the problem is that "images are not loaded into Kozaneba".
- Regroup was able to make image stickies, so it can be done in Kozaneba, but not in time for the study group, so it's not the right time.
- I want to import an already indented bulleted list as a hierarchical group.

Look at the test code and identify what's missing from the test.
- Checking the position of the drag result
- Scroll and Zoom
    - Hotkey Testing
- Make sure it's deleted when you delete it in the context menu.
- Opening and Closing Groups
- Edit Group Title


[/kozaneba-forum-jp/release-note](https://scrapbox.io/kozaneba-forum-jp/release-note).
2021-08-26
- user dialogue
    - List of existing places sorted by update time
    - New "place" can be created.
        - Same when accessing `/#new` while logged in
- Group padding can be adjusted.
    - Considering whether to reduce the default value.

I was thinking about arrows, and I tend to think only of the relationship between two terms implicitly, but it could be between N terms separately.
![image](https://gyazo.com/3ff617ca88ff2971f955498c4a490022/thumb/1000)

---
![image](https://gyazo.com/9375715516dbb7ae01077f30f78b2294/thumb/1000)

- I tagged the WIP task as WIP.
    - Maybe make this one stand out, like a red background or something.
    - ![image](https://gyazo.com/b202a0b941bbc79c1a9ef348b654a89e/thumb/1000)
    - `background: blue; color: white;`
    - The ability to add custom styles would be nice.
- I've tried reducing the group's margin, and it's mostly good, but there are two problems
    - Empty groups are garbage.
        - > Should the "empty group" exist in the first place, or should it disappear [src [https://scrapbox.io/nishio/2021-08-26Kozaneba%E9%96%8B%E7%99%BA%E6%97%A5%E8%A8%98#61275c3daff09e](https://scrapbox.io/nishio/2021-08-26Kozaneba%E9%96%8B%E7%99%BA%E6%97%A5%E8%A8%98#61275c3daff09e) 00006ef90e]
        - But I'd like to express "no bugs so far" in an empty "bugs" group.
            - If it has a title, it won't disappear?
        - Is the reason you get so many empty groups because you're adding one more piece to the group in the first place?
            - No, there are times when you add two or three more cards, so even if you only deal with the case of one card, you still make garbage.
        - Is it still appropriate to "automatically delete empty groups with no title"?
    - Difficult to click on a group instead of a middle kozane when the width or height of one kozane is
        - min-width / min-height

![image](https://gyazo.com/c4a365485a2f7dd8cb4bd3fcde440cd4/thumb/1000)

Try reducing the margin (padding to be exact).
- There's a lot to be learned from actually using it.
- Change with user scripts for easy trial.
- If it doesn't work, I can go back to it right away, so it's easy.
    - Oh, this is the same phenomenon as [[feature toggle]]?
- There is a stream of thought that leads to it around what eventually became the task (the larger kozane).
    - So it may change by sticking with other things before actually starting the project.
    - In fact, "delete empty groups" has been changed to "delete empty groups without titles".

I think I'll make the release notes kozaneba tomorrow...

User Extension Demo
- Do the unexpected with less code than is useful.
- Can you do that?" It's important to be
- Gaming Kozane and Party Parrot
- pomodoro lionfish (Pomodoro unicolor)
- In that sense, Scrapbox's ability to load a linked page and turn it into a kozane by specifying the page is a "convenient feature with a large implementation scale.
    - It's more of a user extension demo...
    - killer application

It looked easy enough to do, so I tried it and did it.
Ability to add custom styling
`kozaneba.update_style("1629979178768", (s) => {s.background = "blue"; s.color = "white" });`
- It's stored properly on the server.

Groups are not reduced below a certain size, even if empty.
![image](https://gyazo.com/460583dc8d0fb83d2203c5222ba47d97/thumb/1000)

When opening a read-only URL, should it say "This is read-only, editing will not save" or not?
- You can default it out, and if you don't like it, you can turn it off with a user script.
- I don't think you should push everything into user scripts!"

For a moment, I thought, "I'll make it configurable via user script and see what users are doing," but that's a sample that's so biased that it shouldn't be used for the purpose of determining default settings for the layperson.


Assuming the arrow function is included.
- Ideally, the arrow connecting A and B would be in the forefront when one of them moves.
- All arrows are in front of the box, and there is also a design
- The design of always being on the back is a bit subtle due to the presence of groups
    - There could be "point to the box in the group."
    - What's inside is basically a front over what's outside.


I put the release notes into Kozaneba for testing.
- is lumped in with "date and time", there is nothing more that can be done about it.
- I can't sort out the ones that are far apart in timeline but close in meaning.
- If you throw out the date and time and the chronological flow, you can organize it by meaning.
    - But users must have psychological resistance to abandoning the axis of "something that is already organized on a certain axis".

- There's also a way to use arrows to represent the relationship between distant objects.
    - Something about the project looks familiar...
    - [https://labs.cybozu.co.jp/blog/nishio/2007/06/pythongrinedit.html](https://labs.cybozu.co.jp/blog/nishio/2007/06/pythongrinedit.html)

next  [[Kozaneba Development Diary 2021-08-27]]

---
This page is auto-translated from [/nishio/Kozaneba開発日記2021-08-26](https://scrapbox.io/nishio/Kozaneba開発日記2021-08-26) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.