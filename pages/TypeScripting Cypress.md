---
title: "TypeScripting Cypress"
---

I was using the default JS for the time being, but when I did [[Update with immer and test with Cypress]], I immediately Typo'd it because completion did not work with type, so I concluded that [[TypeScript]] in [[Cypress]] was a must. I concluded that [[TypeScript]] is a must for [[Cypress]].

![image](https://gyazo.com/aa50d968a68da1936e93ddd738262053/thumb/1000)

Convert it to TypeScript by referring to [TypeScript | Cypress Documentation](https://docs.cypress.io/guides/tooling/typescript-support#Install-TypeScript).

I saw a description that says something like the following, which is not appropriate if you put tsconfig inside the cypress directory, otherwise it ignores the custom command
tsconfig.json

```json
"include": [
  "cypress/integration/*.ts",
  "cypress/integration/**/*.ts",
]
```

It is a relative path, so it looks like this (FULL)
tsconfig.json

```json
{
  "compilerOptions": {
    "target": "es5",
    "lib": [
      "es5",
      "dom"
    ],
    "types": [
      "cypress"
    ]
  },
  "include": [
    "*.ts",
    "**/*.ts",
    "../src/*.ts",
    "../src/**/*.ts",
  ]
}
```


When I tried to import *.tsx, I got an error that --jsx is required, but I decided to keep it simple since it was unclear whether I needed to be able to import tsx for this use case in the first place.

Typo is now properly alerted if you `import { State } from "reactn/default";` and declare the type.
![image](https://gyazo.com/cbbf38921672d36603034a047fa6e03c/thumb/1000)

By the way, about the `@ts-ignore` thing,
If `cy.window().its("movidea").then((movidea) => { ... }`, the argument is any,
`cy.get("@movidea").then((movidea) => { ... }` would be `JQuery<HTMLElement>`.

It is inconvenient to cast movidea every time.
Create custom commands or

I tried to follow the sample, but I had some problems like `Type 'Chainable' is not generic.` or `Property 'movidea' does not exist on type 'cy & EventEmitter'. I had a bit of trouble getting it to work, but I finally got it to work.
cypress/support/index.ts

```typescript
/// <reference types="cypress" />
import { TMovidea } from "../../src/exposeGlobal";

declare global {
  namespace Cypress {
    interface Chainable {
      movidea(callback: (movidea: TMovidea) => void): Chainable;
    }
  }
}

Cypress.Commands.add("movidea", (callback: (movidea: TMovidea) => void) => {
  return cy.window().its("movidea").then(callback);
});
```


I found the following in [official document](https://docs.cypress.io/guides/tooling/typescript-support#Types-for-custom-commands), but doesn't this cause an error?
ts

```typescript
declare namespace Cypress {
  interface Chainable {
    /**
     * Custom command to select DOM element by data-cy attribute.
     * @example cy.dataCy('greeting')
     */
    dataCy(value: string): Chainable<Element>
  }
}
```

I checked the Cypress source.
ts

```typescript
declare global {
  namespace Cypress {
    // TODO: Why is Subject unused?
    // eslint-disable-next-line @typescript-eslint/no-unused-vars
    interface Chainable<Subject = any> {
      ...
```

So, I supplemented global and it works as expected.

Finally, in the test code, I could write this. It looks like a destructive update, but it is a non-destructive update using immer, and the redrawing by the React hook runs properly.
test.ts

```typescript
    cy.movidea((movidea) => {
      movidea.updateGlobal((g) => {
        g.itemStore["1"].position = [100, 0];
      });
    });
```


---
This page is auto-translated from [/nishio/CypressのTypeScript化](https://scrapbox.io/nishio/CypressのTypeScript化) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.