---
title: "Kozaneba Development Diary 2021-09-02"
---

from  [[Kozaneba Development Diary 2021-09-01]]
2021-09-02Kozaneba Development Diary

release notes
- When a group with a title is ungrouped, an empty group with that title remains in the upper left corner.
    - The title used to be the new Kozane.
        - This is the thought that the "title given to the group" should not be erased because it is a newly created summary of the group
    - By leaving them as a group rather than a kozane, for example, if you want to put half of a group with several elements into another group, you can ungroup, select half of the elements and put them into the original group, and put the other half into another group.
    - ![image](https://gyazo.com/c1dca0c13c52d22defed38e53e39921b/thumb/1000)

release notes
- Fixed paste bug

I've added the ability to delete a place to the developer menu for now.
- When I delete and reload, I get an error dialog saying "no
- Change subscriptions expire
    - It detects this and turns off the autosave.
    - Turn it on again and it will save a new one with a different key.
- Looks like you can let the user use it directly.

release notes
- Delete Place function

release notes
- link to site of a crime syndicate's hidey hole
    - if `custom.url` in kozane is neither empty string nor undefined:.
        - A link icon appears in the upper right corner and `visit` is added to the menu

I put minSize on the group, but there will be cases where it's "too picky and hard to select".
- What to do.
- Judged by area?

release notes
- Kozane with `custom.url` is created when pasting a URL
    - The string to be displayed can be edited from the context menu after pasting.


Can "make part of a Ba into another Ba."
- What you copy becomes JSON and goes into the clipboard.
- Can be pasted into other Ba
- So just "select, copy and paste into a new Ba".
- Whether to make this one menu item or not.
    - I don't think it's something you use that often.
- If you are going to make it, make it reusable with user extensions.
    - Getting a Selection as JSON
    - Write JSON to new Ba to get ID
- Two of the following are required


I'm going to use it for something else.
- pKeichobot
- pIntellitech

Exit from selection mode if selection is empty

Crash after copy-pasting an unnamed group and then ungrouping the group inside

release notes
- Fixed a bug in Firestore permission rules.
    - Read-only shared Ba could be deleted by executing the delete command from the development menu by starting the development server locally.

I'll need a local backup.
- It seems not difficult, since we have the ability to convert to JSON and the ability to restore it by pasting it by the user.
- Every 15 minutes or so, compare it to the last backup and if it has been updated, save it to the local IndexedDB.

release notes
- Fixed problem with no place to grab to drag groups when lined up exactly in a rectangle when adding kozane

Hmmm...
ts

```typescript
const p = get_group(getGlobal(), parent);
if (p.items.length === 0 && p.text === "") {
  updateGlobal((g) => {
    remove_item(g, parent);
  });
} else {
  normalize_group_position(parent);
}
```

There are three different component constructions...

- A: internally updateGlobal: normalize_group_position
- B: receive a draft and destructively update it: remove_item
- C: no destructive updates, so draft or not: get_group

Hmmm, shall I make draft the second argument to receive and "if omitted, make it yourself"?
ts

```typescript
export const normalize_group_position = (gid: ItemId) => {
  updateGlobal((g) => {
	...
  });
};
```

Here.

do (auxiliary used in place of "-masu" after a -masu stem)
ts

```typescript
export const normalize_group_position = (gid: ItemId, draft?: State) => {
  const body = (g: State) => {
    ...
  };
  if (draft === undefined) {
    updateGlobal(body);
  } else {
    body(draft);
  }
};

```


furthermore
ts

```typescript
export const normalize_group_position = (gid: ItemId, draft?: State) => {
  optional_draft(draft, (g) => {
	...
  });
};

const optional_draft = (
  draft: State | undefined,
  f: (g: State) => void
): void => {
  if (draft === undefined) {
    updateGlobal(f);
  } else {
    f(draft);
  }
};
```


Now the `optional_draft` part is common and you only need to rewrite the first two lines of the utility that does not accept existing drafts

[https://twitter.com/nishio/status/1433356592620081155?s=20](https://twitter.com/nishio/status/1433356592620081155?s=20)

- [[Arrows are a way to express clear relationships and make them unbreakable]]

- [[Scrapbox-like management of source code]]

Oh, I see.
- When I save a read-only shared Ba (for which I have editing privileges) as an alias and another user edits it, my editing privileges are saved at the "save as" stage, so it appears in my list and can be rewritten.
    - This behavior is odd.

next:  [[Kozaneba Development Diary 2021-09-03]]

---
This page is auto-translated from [/nishio/Kozaneba開発日記2021-09-02](https://scrapbox.io/nishio/Kozaneba開発日記2021-09-02) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.