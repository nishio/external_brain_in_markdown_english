---
title: "Regroup2019 Technology Summary"
---

Summarize the elemental technologies of [[Regroup]] made in 2019: [[pRegroup-done-2019]].
- cf.  [[Technologies to be learned on the React axis in 2020]]

- [[TypeScript]]+[[React]]+[[Webpack]]
    - TypeScript: [[Visual Studio Code]] uses type information for completion and error detection, which is by far better than raw JavaScript
        - [Re-introduction to TypeScript "TypeScript without hard work", making JavaScript a "soft" statically typed language (written by gfx) - EngineerHub｜Careers for Young Web Engineers!](https://employment.en-japan.com/engineerhub/entry/2019/04/16/103000)
        - a (T1 | null)
        - a! (T1)
    - create-react-app
        - `$ npx create-react-app <my-app> --typescript`
            - They make a template for the app and I'm following it honestly.
        - [https://github.com/facebook/create-react-app](https://github.com/facebook/create-react-app)
    - Webpack:
        - `$ npm start`
            - [https://webpack.js.org/configuration/dev-server/](https://webpack.js.org/configuration/dev-server/)
            - A development server is started up locally.
                - [DevServer | webpack](https://webpack.js.org/configuration/dev-server/)
            - Automatically builds when you edit the source
            - It also comes with browser auto-reload for convenience.
            - I haven't done it, but it can be set to serve with HTTPS, so it's easy to develop JS customization for the product.
        - `$ npm build`
    - React
        - I'm not particularly picky.
        - Maybe DOM-based apps would be good for reusing components.
            - Regroup is an app with a big HTMLCanvasElememt that is not being utilized much.
            - balloonMenu
            - I didn't use it in Regroup, but I used [[styled-components]] in another app and it was rather good!
        - Third-party components may be useful
            - Modal dialogs and the like.
                - [[ReactModal]]
        - How state updates cause the view to be redrawn
            - Philosophy of not directly manipulating the DOM
            - There are still cases where it doesn't work.
                    - [[iPad may ignore focus]]

- [[paper.js]]
    - pass draw] in HTMLCanvasElememt
    - Smoothing out the written lines is thrown into this.
        - I hate rattling lines, so the smoothness of this feature on the iPad was a deciding factor in my decision to use this.
        - [The shape of the path is wrong.
        - strokeCap = "round"
        - lineJoin = "round"
    - The lasso selection is accomplished by a boolean operation on the path.
            - [[Lasso selection of stickies and paths]]

- [[Firestore]]
    - Document-oriented DB + Subscription via [Websocket
    - A listener is called when a value on the server changes, making it easy to prototype a small information-sharing application.
    - They accumulate it offline locally and save it when they get online.
        - However, don't be alarmed if you reload the browser, as it will be lost and will not resolve conflicts during co-editing, etc.

- hosting
    - It was just static hosting, so I'm plugging it into [[Amazon S3]] and serving it over HTTP.
    - It would be nice to use something like [[Netlify]], which I learned about later.
        - > npm i -g netlify-cli and upload the directory specified by netlify deploy -d public --prod to netlify
        - > Deployed static sites are deployed on CDN
        - > A hashed URL is generated for each build, and if the deploy ID is known, the current one can be accessed.
        - >  It also includes FaaS like Firebase Function. The contents are AWS Lambda
        - [2020, Technologies to Learn on the React Axis - mizchi's blog](https://mizchi.hatenablog.com/entry/2020/01/04/172041)

- [[Apple pencil]]
    - Distinguishing between touch: [[Distinguishing between direct touch and Pencil touch on the iPad]].
    - For me, who is used to Apple pencil, it is more natural to distinguish between the two, but looking at the behavior of users who are not used to it, I guess I need to pay a little learning cost.

- Smooth scaling
    - The goal was to digitize the KJ method, which is done with a desk and sticky notes, so it was necessary to be able to smoothly zoom in and out and move around with about 200 sticky notes out on the iPad.
    - At the start of the two-finger gesture, the contents of the Canvas are set to HTMLImageElememt and left to the browser's own rendering instead of JS
    - Related: [[Zoom and translate with two-finger gesture]].

- React-like state management
    - How state updates cause the view to be redrawn
    - Do not update state objects destructively
        - Because changes in status are judged by identity, not content
    - Incompatible with tree representation of parent-child relationship of drawing target
        - Destructive updating is not possible, so if a child is updated, all ancestors must be updated as well.
        - So implemented.
        - Is that good enough?
    - React-like state of React function components is function scope
        - Pass update functions to child components as arguments
        - I want to update it in the mouse event handler, so I need to pass it there, but it's a hassle.
    - I'm a little confused about how to handle this situation, and it's not a very good design.
        - I was thinking of moving to [[Redux]]. I was thinking about moving to [[Redux]], but [[reactn]] seems better.
            - [Context - React](https://reactjs.org/docs/context.html) mechanism wrapped for ease of use

- UNDO implementation
    - We consider it an essential feature.
    - It simply keeps a history of all snapshots.
        - State that if performance problems arise, we will consider it.
            - [[undo implementation]]
    - React state updates and UNDO units were identical, but this is not good
    - The granularity of UNDOs natural to humans is different from the basic unit of state update
        - For example, if you select multiple objects and move them:.
            - A natural implementation of state update is to perform "one object position update" on the selected object.
            - If we make this update unit the unit of UNDO, "one object returns to its original position."
            - This is not natural to man.

- Image Handling
        - [[canvas pollution]] Issue.
        - I can display images on other servers.
        - Some response headers make subsequent export impossible (security restrictions)
    - Image blinking problem
        - There is a difference in behavior between Chrome and Safari (and Chrome on iPad).
        - When redrawing a map with an image on it that is subsequently edited, Safari discards the local image and fetches it from the net.
            - As a result, all image stickies blink on every move.
        - This can be suppressed by making sure that the response header is well cached.
        - [[Canvas Pollution Solution Edition]]
        - Create a proxy server to solve both problems

- screen size
        - [[Using Conditional Branches, Variables, and Calculations with CSS]]
        - [[100vh, it sticks out vertically.]]
        - [[Menu icons stick out on narrow screens such as iPhone]]

- zoom
        - [[If you draw with a pen while zoomed out, it rattles.]]
        - [[Keep the line thickness constant.]]

    - [[Add a callback to be called after updating Paper.js]]

- mouse event
    - Paper.js has a mechanism for Tool switching.
    - The object that receives mouse events is switched.
    - This is used to switch between movement mode, pen mode, and lasso selection mode.
    - But you'd still want to move around in pen mode...
    - Looks like I better get organized.

    - [[Balloon Menu]]
    - float in the DOM
        - [[Lasso selection → Delete]]

    - [[Automatic font size adjustment for stickies]]
        - [[g sticks out at the bottom]]
        - [[OKR problem]]


[[Regroup2019]]

---
This page is auto-translated from [/nishio/Regroup2019の技術まとめ](https://scrapbox.io/nishio/Regroup2019の技術まとめ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.