---
title: "2021-07-14Movidea Development Diary"
---

Today's Picture of the Day
![image](https://gyazo.com/e1f53457d5b6464ee09d9353282f24e7/thumb/1000)

prev  [[2021-07-13Movidea Development Diary]]
Cypress, contains selects DOM but type is undefined
ts

```typescript
cy.get("div[data-testid='2']").should((x) => {}); // x is JQuery<HTMLElement>
cy.contains("A B").should((x) => {}); // x is undefined
```


This is due to the implementation of both as a way to retrieve the DOM and as an assertion.
It looks like this, but the cy is `Chainable<undefined>`, so `Subject=undefined`. Bad design, the names should be separated.
cypress.d.ts

```typescript
contains(content: string | number | RegExp, options?: Partial<Loggable & Timeoutable & CaseMatchable & Shadow>): Chainable<Subject>
contains<E extends Node = HTMLElement>(content: string | number | RegExp): Chainable<JQuery<E>>
...
interface cy extends Chainable<undefined> {}
```


Aside from that, I have data-testid attached to my implementation, so I thought I would make it easier by using it to make the selection a custom command.

support/index.ts

```typescript
declare global {
  namespace Cypress {
    interface Chainable {
      ...
      testid(testid: string): Chainable<Element>;
      hasPosition(x: number, y: number): Chainable<Element>;
    }
  }
}

Cypress.Commands.add("testid", (testid: string) => {
  return cy.get(`*[data-testid='${testid}']`);
});

Cypress.Commands.add(
  "hasPosition",
  {
    prevSubject: true,
  },
  (subject: Cypress.Chainable<Element>, x: number, y: number) => {
    const cr = subject[0].getBoundingClientRect();
    expect(cr.x).equal(x);
    expect(cr.y).equal(y);
    return subject;
  }
);
```


with this
`cy.testid("1").hasPosition(159, 174);`
I can now write.
However, this is not retried.

In fact, [Custom Commands | Cypress Documentation](https://docs.cypress.io/api/cypress-api/custom-commands) describes how to create child commands, but the examples do not make assertions. The example does not make any assertions.

If you look at [Assertions | Cypress Documentation](https://docs.cypress.io/guides/references/assertions#Adding-New-Assertions), it says to add an assertion to [[Chai]]. Chai].
[Adding Chai Assertions [https://github.com/cypress-io/cypress-example-recipes/tree/master/examples/extending-cypress__chai-assertions](https://github.com/cypress-io/cypress-example-recipes/tree/master/examples/extending-cypress__chai-assertions) I wrote this in reference to [].
support/index.ts

```typescript
chai.use((_chai, utils) => {
  function hasPosition(options) {
    const [x, y] = options;
    const cr = this._obj[0].getBoundingClientRect();

    this.assert(
      cr.x === x,
      `expected x:${cr.x} is ${x}`,
      `expected x:${cr.x} is not ${x}`,
      cr.x
    );
    this.assert(
      cr.y === y,
      `expected y:${cr.y} is ${y}`,
      `expected y:${cr.y} is not ${y}`,
      cr.y
    );
  }

  _chai.Assertion.addMethod("hasPosition", hasPosition);
});
```

with this
`cy.testid("1").should("hasPosition", [159, 174]);`
I can now write.
If it were a should, I'd say it's a have, but that's a Chai thing to say in the first place.
`cy.testid("1").has.position([159, 174]);`
I started to feel as if I should be able to write "I'm sorry, I'm sorry, I'm sorry, I'm sorry," but this was around the border between Cypress and Chai, and the conversation was complicated, so I held off.

The following test can now be written concisely
test.ts

```typescript
// before
cy.get("div[data-testid='1']").should((x) => {
  expect(x[0].getBoundingClientRect().x).equal(x1);
  expect(x[0].getBoundingClientRect().y).equal(y1);
});
// after
cy.testid("1").should("hasPosition", [x1, y1]);
```


I'm getting used to custom commands a lot, and I realized that I should make updateGlobal a custom command since I use it so often in the first place.
support/index.ts

```typescript
Cypress.Commands.add("updateGlobal", (callback: (g: State) => void) => {
  return cy.movidea((movidea) => {
    movidea.updateGlobal(callback);
  });
});
```


It is now possible to update the status without having to go through movidea every time, as shown below.
test.ts

```typescript
// before
cy.movidea((movidea) => {
  movidea.updateGlobal((g) => {
    g.itemStore["1"].position = [dx, 0];
  });
});
// after
cy.updateGlobal((g) => {
  g.itemStore["1"].position = [dx, 0];
});
```


The test is "If item #3 (sticky B) is moved, the position of item #1 (group) should be where and where and where. (I should have used an easy-to-understand name for the item ID, too.)
test.ts

```typescript
cy.updateGlobal((g) => {
  g.itemStore["3"].position = [-100, 0];
});
cy.testid("1").should("hasPosition", [55, 170]);
```

![image](https://gyazo.com/4dbdecd6194f095b8cb9127af8d6fb9a/thumb/1000)

And when the group is closed from this state, the location shifts. Let's fix this next.
test.ts

```typescript
cy.updateGlobal((g) => {
  (g.itemStore["1"] as GroupItem).isOpen = false;
});
```

![image](https://gyazo.com/1d073cc26748ada8d0a52dd54919dad8/thumb/1000)

Cypress, I could see snapshots of each stage of the test so I could check for "bugs that are slightly off by 4 pixels", useful!
![image](https://gyazo.com/085db82b0e553d535a2d7c4cc66c69ae/thumb/1000)

Let's display the JSON exported from Regroup again at this point. Now that we've got it right, it's easy to see what's causing the bug: the bounding box for the group within a group is losing the information about the parallelism.
![image](https://gyazo.com/9283591c224d11aa269132886d2a7230/thumb/1000)

Fixed. It spills over into a lot of different areas, but it's good to have a test case so it's easy to check how it works. It now looks decent.
![image](https://gyazo.com/e1f53457d5b6464ee09d9353282f24e7/thumb/1000)
Visible in Regroup from [[2021-07-01#60df19d4aff09e0000c6d717]].
![image](https://gyazo.com/0d1187d7fe01b6a4de30333c80c1948e/thumb/1000)
Almost the same!
All test cases so far are also successful.


Tomorrow I'll work around menus and dialog.
[https://material-ui.com/components/menus/](https://material-ui.com/components/menus/)
I reread [[OOUI]].
I was re-reading the OOUI description, and both "New" and "Import" are task oriented.
What if we were to make it an object oriented UI?
I wonder if the import wizard should be open from the beginning, since it's obvious that it's a "new creation" when you access a non-existing map URL, and it's unlikely that you don't put in content after creating a new map.


I think it's "add sticky", not "import".
- What is the UI for importing from a URL?

Next  [[2021-07-15Movidea Development Diary]]

---
This page is auto-translated from [/nishio/2021-07-14Movidea開発日記](https://scrapbox.io/nishio/2021-07-14Movidea開発日記) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.