---
title: "2021-07-26Movidea Development Diary"
---

prev  [[2021-07-20Movidea Development Diary]]
![image](https://gyazo.com/f5ec0d0c1f2416f023576d43b5924157/thumb/1000)
---

[Twitter](https://twitter.com/nishio/status/1419295427849977859?s=21)
- If dog-footing is useful in software development, then it could be useful in mentoring, too. and this year I'm trying to do the presentation material preparation that is assigned to the adopters myself, and when I do that, I say, "I'd better do user testing before the midterm presentation," but I feel that "mine is not yet ready to be tested..."
- In other words, this means that there is a discrepancy between the timing that the creator thinks is appropriate for user testing and the timing that the person watching from the side thinks is appropriate. Since the creator can predict "it will be better if I implement this a little more," the creator prioritizes immediate implementation over user testing, which is unpredictable (self-discipline).
- This time I decided to rebuild after the announcement of the start of the project, so I am tempted to think "it's not ready for user testing yet", but this is typical "[[Looking for reasons not to]]". Even if it is not appropriate to do it now, I should think about what needs to be done or break down the task to validate it as soon as possible
- The reason why we do user testing is to "test a hypothesis."
    - (In some cases, we don't even realize we've created them, but we just assume they must be true.)
    - You can't test everything because testing a hypothesis is costly.
    - Therefore, I think the priority of verification is determined by multiplying the probability of "If we proceed with the project without verifying this, we may incur a large rework loss" and the amount of loss.
- In that sense, my hypothesis for the last Regroup was "The method I found valuable on paper must be even more valuable in electronic form." I created a prototype while learning React and TypeScript, and my hypothesis was verified when I became a repeat customer myself. But I need to verify if it has value for other people as well.
- When I tried to do user test with Regroup as it is, "2 non-intuitive operations are required to create a new one, and also a difficult-to-understand operation is required to get to the recommended initial state" is bad, and the assumed device "iPad + Apple Pencil" is also tough, so I had to rework it.
- Therefore, I think the first thing to be verified is "can first-time users start using the system without being confused? This is followed by the question of whether the first-time user will feel the value. It is impossible for people to feel the value of a tool if they cannot start using it, so the first priority is to start using it.


New dialog should appear when you click on the New link
- Should it be similar to the add sticky dialog but separate?
- Let's paste a multi-line text, and I'll provide you with the text?
    - word
    - Short Phrases
    - This is a short sentence
    - This is a very, very long sentence, so if you make it into a sticky, the text will be small!
- The "should be chopped to a reasonable length" is too burdensome for first-timers.
    - Because once you don't move on, you don't understand "why it's necessary."
- Carving lines that are too long
    - Do you want to do it automatically?
    - Check box for default ON?
- Tutorial balloon out?
    - Should I have one?
    - Wouldn't it be nice to see video help page by page instead of ballooning it out?
    - Oxygen Not Included style

When multiple stickies are added, should they be separate stickies or grouped together?
- Convenient when grouped together.
    - Intuitive repair when accidentally added on top of an existing sticky
- Disadvantages of being grouped
    - First time users suddenly become "select and release the group first".
    - No, don't you?
        - Don't ungroup them, just move them as they're grouped.
        - You can drag it out of the group.
        - You can keep all the "imported but unused" items together and tucked away beside you.
→ Grouped and OK.

> "Two non-intuitive operations are required to create a new one, and another operation is required to get to the recommended initial state, which is not easy to understand the correct answer" is bad.
- Reflecting on why it happened
- Access to the URL root is now a link placement.
    - ![image](https://gyazo.com/d7bf516ac4f588a674a99db6e0b2696a/thumb/1000)
    - Router Design Issues
    - Initially, I tried to do the help itself in Regroup.
    - I put a link to a sandbox or something that won't be saved.
    - New creation is not saved in the cloud.
        - Why?
        - Create New Link
            - [https://regroup.netlify.app/#/blank](https://regroup.netlify.app/#/blank)
        - ![image](https://gyazo.com/08ff543690907be4bf19e83e8ac5c55a/thumb/1000)

        - Create Blank Map
        - Cloud Saved Links
            - example: [https://regroup.netlify.app/#/key=hppNrkDvUWx2UFNKwrpG](https://regroup.netlify.app/#/key=hppNrkDvUWx2UFNKwrpG)
            - Open in a new tab
            - Change to dialog later because popup is blocked by environment

What the routing should be
- Since the first time person is/will come to the site, the tutorial should start there without making them choose from the extra "options".
    - Regroup is not good because it only has a list of poorly explained links
    - Movidea is a blank screen with no net connection
        - This is useful for testing and should be kept, but it shouldn't be in such a prime location.
- Capability URL] to allow editing without the need to log in.
    - I should have known view and edit by URL.
    - In the Google Docs metaphor, it would be interesting to have "separate layers for commenting" in addition to view and edit, but this will be an experiment for later.

`$ npx cypress open`

:

```
You are currently running Version 7.7.0
To get the latest, run the following command*:
npm:npm install --save-dev cypress@8.0.0
```


View Regroup code
- I'm trying to figure out how to do routing, so I'm using react-router, but it doesn't match my typical use case, so I end up handling the hash values myself.
- The typical use case is to have multiple pages, but my app is a single page, and when another screen is needed, it is not a page transition, but a dialog, so it does not fit into the typical use case.
ts

```typescript
import { Route, RouteComponentProps } from "react-router";
import { HashRouter } from "react-router-dom";
...
    <HashRouter>
      <Route path="/:id" component={WhenHashSpecified} />

      <Route exact path="/">
      ...

...
const WhenHashSpecified: React.FC<RouteComponentProps<{
  id: string;
}>> = props => {
  return <App urlParam={props.match.params.id} />;
};

```


So I implemented the routing part.

I changed `cy.visit("/")` to `cy.visit("/#blank")` in the test code, and the test was broken.
The reason for the rub is that `cy.visit("/#blank")` does not reset the state of the app.
- I was in the middle of the test code and did a VISIT with the intention of resetting the status, but it didn't.
- Therefore, an error occurs when trying to draw a new screen with the previous range selection dragging on.
- Moreover, it looks as if the problems that occurred there affected the next test case.
Huh? Why doesn't it reset?
- I thought `cy.visit("/")` reset it, right?

In (A) after `cy.visit("/")` the state is reset, but in (B) after `cy.visit("/#blank")` the value is not reset
ts

```typescript
describe("visit_reset", () => {
  beforeEach(() => {
    cy.visit("/");
  });

  it("main", () => {
    cy.updateGlobal((g) => {
      g.scale = 2;
    })
    cy.getGlobal(g => g.scale).should("eql", 2);

    cy.visit("/");
    cy.getGlobal(g => g.scale).should("eql", 1);  // (A)

    cy.updateGlobal((g) => {
      g.scale = 2;
    })

    cy.visit("/#blank");
    cy.getGlobal(g => g.scale).should("eql", 2);  // (B)
  });
});
```

reported [https://github.com/cypress-io/cypress/issues/17479](https://github.com/cypress-io/cypress/issues/17479)

Assigned a new URL to the page for testing, and when the root is accessed, it now starts with the add sticky dialog open.

Next, add multiple sticky notes.
- Dialogue is on.
- Grouping

after that
- Move single stickies by dragging (only groups for now)
- From inside the group to outside the group
    - I want to highlight if the drag target is a group

- Added to the figure in [[2021-07-20Movidea Development Diary]].
![image](https://gyazo.com/036de58bf7b1abc5d6a47f4b38a7f90d/thumb/1000)
Hmmm, I need to do something about the notation.
- event handler
- processing to be performed
- Relationship to be stopped by stopPropagation depending on the inclusion of the element
- Dynamic scope of time series
![image](https://gyazo.com/3a2bfb6046f1470934bdb5fba8925ace/thumb/1000)

stopPropagation, it doesn't need to stand out like that, also the dynamic scope should be clearer, and it's not good to recognize the same thing by having the same color, it should have a name.

Now "selected" is determined by "does the selected object exist", but should the selection indicator be turned off when there is no object in the selection, or should it be possible to enter the selected state even if there is no object to be selected?
- I think the latter is more natural.

It was not a good idea to reuse the code to try to render the closed group faceplate stickies as if they were normal stickies.
- Type error when trying to specify a drag target because the id is now a string instead of an ItemId so that it can be reused.
- The unit of reuse was incorrect.
- Components separated into Fusen and NameplateFusen
- Commonly needed font size adjustment processes are handled by custom hooks.

Need to make sure that the sticky's dragstart does not propagate to the parent group.
- Red line in the figure
    - ![image](https://gyazo.com/63941a044cdf9b823c4d5fa040344dff/thumb/1000)


It's done.
![image](https://gyazo.com/f5ec0d0c1f2416f023576d43b5924157/thumb/1000)
- I hope we've now moved the Regroup equivalent.
- Figure Update
    - ![image](https://gyazo.com/d4f212e311dace98f0186f8535241eb3/thumb/1000)
- Right now, the group is not receiving drops, so the drop is happening on the canvas through and through.
    - If you drop this in the group, it should be processed now, and if you drop it on the canvas, it should be taken out of the group.

I found a pattern.
- ![image](https://gyazo.com/64a50b4a3cb7324d1ccc4339da5d680a/thumb/1000)
- I want to do different processing with a common event handler.
    - Including one of them being "no process".
- At this time, the "which process" information must be obtained from outside the event handler, i.e., dynamic scope

If the behavior changes depending on whether it was dropped on a canvas or a group, the user needs to know which one it is now.
![image](https://gyazo.com/e0840d722c87482ee1c5143acfd1c8e3/thumb/1000)
This implementation required processing not shown in the illustration.
![image](https://gyazo.com/f87038d9dd418529f5805f9cfd2e9773/thumb/1000)
- When there is another element in the drop target, the dragleave event is fired.
- Determine if it went out in a reference-counting way, since the dragenter happens first.

ts

```typescript
  let enter_count = 0;
  const onDragEnter = (e: React.DragEvent<HTMLDivElement>) => {
    enter_count++;
    if (self.current !== null) {
      self.current.style.borderColor = GROUP_HIGHLIGHTED_BORDER_COLOR;
    }
    e.stopPropagation();
  }
  const onDragLeave = (e: React.DragEvent<HTMLDivElement>) => {
    enter_count--;
    if (self.current !== null && enter_count === 0) {
      self.current.style.borderColor = GROUP_BORDER_COLOR;
    }
    e.stopPropagation();
  }
  const onDrop = (e: React.DragEvent<HTMLDivElement>) => {
    if (self.current !== null) {
      self.current.style.borderColor = GROUP_BORDER_COLOR;
    }
    onGroupDrop(e, value);
  }
```


- [[2021-07-27Movidea Development Diary]]

---
This page is auto-translated from [/nishio/2021-07-26Movidea開発日記](https://scrapbox.io/nishio/2021-07-26Movidea開発日記) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.