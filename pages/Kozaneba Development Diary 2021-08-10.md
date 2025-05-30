---
title: "Kozaneba Development Diary 2021-08-10"
---

One of the Day, Automatically Test the Tutorial
![image](https://gyazo.com/705e639aaafce2c1142768a3411b8e8b/thumb/1000)
---

prev  [[Kozaneba Development Diary 2021-08-06]]
- Include Sentry so that information can be obtained when errors occur.
- Hide the development menu from the deployed version
    - Hide the developer menu by default except on localhost
    - Make it an option to take it out.
- We'll cover what we're doing in the tutorial in the test.
    - Careful testing, especially around loading and saving data

Less urgent but important
- Create a dialog to send feedback


In create-react-app development mode, the error handler is registered before Sentry, so it is triggered first
- Error Boundary? Find out

✅Hide the developer menu by default on non-localhost
- I'll make it available in the ✅ option.
- I'll hard code it to let you out if you log in with my account.

[https://reactjs.org/docs/error-boundaries.html](https://reactjs.org/docs/error-boundaries.html)
> Error boundaries do not catch errors for:
- > Event handlers (learn more)
- > Asynchronous code (e.g. setTimeout or requestAnimationFrame callbacks)
That's no good!

Related: [[I was unknowingly clenching an exception.]]
- Oh, right, this is an overlay, so you just close it.

Error report dialog can now be viewed on the development server.
![image](https://gyazo.com/8ea5def65c0278127887dfdbfa6afbc1/thumb/1000)
- I can't find a way to make it optional.
- [https://github.com/getsentry/sentry/issues/4646](https://github.com/getsentry/sentry/issues/4646)
- Oh, you're going to put in the appropriate default values?

I should write "OK" in Japanese so that Japanese people don't have to work so hard to write reports in English.
- ![image](https://gyazo.com/bd1fdaf3195dcda1dc53b59a66f2d09a/thumb/1000)

I thought about using Google Analytics to get an idea of how far the tutorial has been viewed, but I'm not sure if that would be timely enough to make a broad announcement.

memo
- First, we need to be able to automatically test what we are writing in the tutorial now.
- thereafter
    - Added ability to close groups
    - write a test
    - Add to Tutorial
    - Ability to set titles for groups
        - It turns into a kozane when ungroup

The only exposure for testing was in development mode.

---

We'll cover what we're doing in the tutorial in the test.
Recent Test Status
![image](https://gyazo.com/3206c440e3d5a49888c1a5c2ff2e7f99/thumb/1000)

![image](https://gyazo.com/c95ed0b11dbfc348cc47e370f4e20181/thumb/1000)
ts

```typescript
    cy.contains("Add Kozane").should("exist");
    cy.contains("Close").click();
```

This is because there are a number of elements that contain Close.
It's not shown on the screen, but it's in the other dialogs.
It is better to point to a specific element with a testid.
Because then the implicit assertion would be tested to see if it's on the screen.

ts

```typescript
    cy.contains("Enable Cloud Auto-Save").click();
    cy.testid("save-status").contains("uploading");
    cy.testid("save-status").contains("done");
```

Asynchronous processing, such as uploading and then completing, can be written without explicit wait.

![image](https://gyazo.com/213a48c08f75805098d96e9fbd88fd92/thumb/1000)
- Tested with tooltip text when mouse hovering over status bar icon

I didn't test the font size adjustment and range selection out of the tutorial.
- Following the test case, there is not a single kozane in the range selection phase.
- I'd have to add it separately, but I think it would confuse people too, so I'm going to change the flow.
- I'll bring up the font size adjustment here.
    - Try adding text containing sample, longer sentences at
    - In the future, a split function for longer sentences will be included here.
- If you try to achieve this in a tutorial, you will want to specify a preset for the input text
    - I thought the split function shouldn't use the same thing, but maybe it's a bad abstraction to make the dialog common between new additions and replacements.
- If we separate the dialogs, is it too much to have a preset in the Add New dialog?
    - Not really, because if, for example, you add the ability to import from Keicho or Scrapbox in the future, you'll want it to open in the presets.

![image](https://gyazo.com/e5d85c3b70c1d5eb22569f92a94edd0a/thumb/1000)
---
Tutorial content can now be inserted during the tutorial as about 50 stickies.
It would be good to add a page about the group after this

I wrote about the group release and wondered if opening/closing and titling groups would be included here in the future..,
So if it's not necessary for the story at this point, there's no need to include it here in the future,
It is better to let the tutorial arrive at a point where it is minimal and complete, and then allow additional reading for knowledge that is not essential.

In that sense, now there is no explicit end of the tutorial, which is not good.
I'm all done! Congratulations!" We need a page of

It's done.
![image](https://gyazo.com/4f987b91589579ccb6a9db3f23650e2c/thumb/1000)


---

Effective use of stationery requires practice.

You can use a pencil or a keyboard. This does not mean you were born with the ability to use them.
Mastery of stationery strengthens the human intellect more than if it were to operate without it. But it takes practice.

Skills are not acquired by reading textbooks. Skills are not acquired by reading textbooks, but by actually doing things.

Tutorial content was kosaneed.
You have just read the tutorial already structured by the author, but let's re-structure it by adding your own words

Read what others have written and create a kozane from it. Add your own thoughts after reading it. Then structure the whole thing.

Let's make 50-100 small bills about what you think is fun and what you think is interesting at any given time. Then structure them.

![image](https://gyazo.com/73e05bd3ea896f7d699c27e26d4c3c16/thumb/1000)

Next  [[Kozaneba Development Diary 2021-08-11]]

---
This page is auto-translated from [/nishio/Kozaneba開発日記2021-08-10](https://scrapbox.io/nishio/Kozaneba開発日記2021-08-10) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.