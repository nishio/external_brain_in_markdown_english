---
title: "UseGlobal to display dialog"
---

A dialog is a component with an "open/closed" state.
Usually, the state is updated from "components that have no parent-child relationship with dialogs," such as menus.
How to do this.

Proposal 1:.
- Common parent comport keeps state
- Pass child components by props.
- Orthodox approach, but I personally dislike it.
    - I don't agree with the style of passing setter to child components with props.

Proposal 2::
- Dialog has state
FooDialog.tsx

```
const FooDialog = () => {
  const [open, setOpen] = useState(false);
  ...
}
```

- As it is, the setter is trapped in the local scope, so we expose it.
FooDialog.tsx

```
export let openFooDialog: () => void;
const FooDialog = () => {
  const [open, setOpen] = useState(false);
  openFooDialog = () => {
    setOpen(true);
  }
  ...   
}
```

- I've been doing this until recently.

Proposal 3:.
- Dialog useGlobal
FooDialog.tsx

```
export const FooDialog = () => {
  const [dialog, setDialog] = useGlobal("dialog");
  const open = dialog === "Foo";
  ...
}
```

- Instead of setting the "open" variable of "boolean" directly to "global", a variable has been introduced to mean "open dialog".
    - Implementation reflects the assumption that only one dialog is open at a time throughout the application.
- Limit values by type to prevent typo, etc.
ts

```typescript
const INITIAL_GLOBAL_STATE = {
  ...
  dialog: null as "Foo" | null,
};
```

- The open side is setGlobal.
ts

```typescript
export const openFooDialog = () => {
  setGlobal({ dialog: "Foo" });
};
```

- I came up with this approach on 2021-03-22.
- At first the code corresponding to `openFooDialog` was placed by the menu, but later it was renamed to this name and moved into FooDialog.tsx
    - It will be clear where the defined dialog is to be displayed.

I'm still not sure what is best, but I thought it would be beneficial to record it at this time when there has been a change in policy, so I recorded it.

---
This page is auto-translated from [/nishio/useGlobalでダイアログ表示](https://scrapbox.io/nishio/useGlobalでダイアログ表示) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.