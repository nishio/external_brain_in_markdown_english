---
title: "Kozaneba Development Diary 2021-08-25"
---

![image](https://gyazo.com/4eeb78aa4bb97227596c1292818a04d8/thumb/1000)
----

prev  [[Kozaneba Development Diary 2021-08-21]]

Note to re-launch the development environment since the OS was rebooted.
- Changed the local directory name from movidea to kozaneba since it was a good opportunity.
- `$ code kozaneba`
- devserver
    - `$ npm start`
- [[Cyperss]]
    - `$ npx cypress open`
- [[Firebase Local Emulator]]
    - `$ firebase emulators:start`
        - PS
        - `$ firebase emulators:start --import firebase_emulator_data`
- Rename each terminal.
    - ![image](https://gyazo.com/5ecf98a8a34b4a7e3964272d3865a4ce/thumb/1000)

- I'll run the test for now.
    - I forgot to export the user data I had in the Firebase auth emulator, so the name I gave to the test account disappeared.
    - ![image](https://gyazo.com/66d23a0209503d9532a506151bdb9277/thumb/1000)
    - ![image](https://gyazo.com/fc45a432d6c7d3b5609356ce6f664806/thumb/1000)
    - `$ firebase emulators:export firebase_emulator_data`
    - `$ firebase emulators:start --import firebase_emulator_data`
        - Oh, I shouldn't have used Ctrl+C to exit? I can't start it.
        - [google cloud firestore - How can I shut down the local firebase emulators? - Stack Overflow](https://stackoverflow.com/questions/62684701/how-can-i-shut-down-the-local-firebase-emulators)
:

```
Check which process is occupying the port sudo lsof -i tcp:<port> 
Kill the process kill -9 <process id>
```

        - Only the Firestore emulator was alive.
            - No -9 on kill.


ts

```typescript
/// <reference types="cypress" />

import { ready_nested_group } from "../../support";

describe("ready nested groups", () => {
  beforeEach(() => {
    cy.visit("/#blank");
    cy.viewport(500, 500);
    ready_nested_group();
  });
  it("do nothing", () => {});
});
```


![image](https://gyazo.com/1a1d9a2a1440c76632313e703c80d417/thumb/1000)
ts

```typescript
  it("do nothing", () => {
    cy.testid("G1").then((x: any) => console.log(x[0].style.cssText));
    cy.testid("G1").trigger("mousedown", 0, 0, { force: true });
    cy.testid("G1").then((x: any) => console.log(x[0].style.cssText));
    cy.testid("G1").trigger("mouseup", 0, 0, { force: true });
    cy.testid("G1").then((x: any) => console.log(x[0].style.cssText));
  });
```


![image](https://gyazo.com/22d18f22e858848fdf031df0738c770c/thumb/1000)

ts

```typescript
  it("should not move when click", () => {
    cy.testid("G1").then((x: any) => {
      const {top, left} = x[0].style;
      cy.testid("G1").trigger("mousedown", 0, 0, { force: true });
      cy.testid("G1").trigger("mouseup", 0, 0, { force: true }).then((x: any) => {
        expect(x[0].style.top).eql(top);
        expect(x[0].style.left).eql(left);
      });
    });
  });
```


---
The problem is that the coordinates are out of order when the context menu is displayed,
- I've noticed that it happens with selections and fixed it, but I'm not sure if it also happens with groups in some cases...
- Caused by code that resets top/left values tweaked while dragging, which also occurs on click
- You've got clicks and drags that are now caused by a form of mouseup/down combination that does its own thing.
- The internal state has not changed, so ignoring it and doing something else will fix it... but normal users will try to fix it if the display is broken...

When I try to title a group of groups, I don't get the text of grandchildren kozane in the default value.
- The default value is "the title of the item in the group is connected to the default value", so a group without a title is just a blank line.

I'll write later in the release notes.
- Include the contents of untitled groups in the default value when editing group titles.
- Fixed a bug where creating a group and deleting a selection was not considered an update and was not saved to the cloud.
- Fixed a bug that caused the display to temporarily shift when clicking to bring up the context menu.
- Improved loading display

Wanted features
- Place list in order of update
- Save Place As
    - Would you like to be able to lead-only at this time?

We'll have to write the Firestore rules properly to make lead-only a reality.

next  [[Kozaneba Development Diary 2021-08-26]]

---
This page is auto-translated from [/nishio/Kozaneba開発日記2021-08-25](https://scrapbox.io/nishio/Kozaneba開発日記2021-08-25) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.