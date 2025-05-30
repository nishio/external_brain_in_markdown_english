---
title: "React"
---

- [https://reactjs.org/tutorial/tutorial.html](https://reactjs.org/tutorial/tutorial.html)
- [https://reactjs.org/docs/hello-world.html](https://reactjs.org/docs/hello-world.html)
- Presentation slides at [Builderscon 2018
    - [https://speakerdeck.com/koba04/algorithms-in-react](https://speakerdeck.com/koba04/algorithms-in-react)
        - React used to implement traverses with recursive calls.
            - Recursive calls cannot be interrupted.
            - Therefore, blocking the UI when it grows large.
            - That's why they're using fiber to make interruptions possible in React these days.
    - Very good explanation of what problems existed in the old implementation, how it was changed, and how it forced library users to change the way they wrote (e.g., asynchronous state updates).
    - Talk about prioritizing side effects.
        - User input events are high priority.
        - So if you do heavy processing there, the input is blocked and the user is uncomfortable.
        - Cutting out to low priority makes user input more comfortable.
        - Runs synchronously during expiration.
    - suspense
        - Error Boundary and Similar Mechanisms
        - Throwing Promises Instead of Errors
        - It is immediately caught inside the library and follows the parent link asynchronously.
        - You can only put out a loading if it takes a long time.
        - It's interesting and seems very important to reduce user stress, but it doesn't seem very dead yet.

Partial Reactization of existing projects
It looks good to start with this temp when making a new one.
[https://reactjs.org/docs/add-react-to-a-website.html](https://reactjs.org/docs/add-react-to-a-website.html)

Build the tool chain only after you feel the need to do so (when it becomes sufficiently complex).
[https://reactjs.org/docs/create-a-new-react-app.html](https://reactjs.org/docs/create-a-new-react-app.html)

onClick is received by handleClick
[https://reactjs.org/docs/handling-events.html](https://reactjs.org/docs/handling-events.html)

Props are read-only
[https://reactjs.org/docs/components-and-props.html#props-are-read-only](https://reactjs.org/docs/components-and-props.html#props-are-read-only)
I see. Separation of model and view.
To update the state, pass a function to this.setState that takes the previous state as an argument, creates a new state, and returns it.

Component called "Circle that changes color when clicked.
[https://codepen.io/nishiohirokazu/pen/YOWqKw](https://codepen.io/nishiohirokazu/pen/YOWqKw)

Too many things can be done in the browser without creating your own development environment, which makes it a hassle to create your own development environment, but it is also hard to develop all the time only in the browser. But that's not an option.
[https://reactjs.org/tutorial/tutorial.html#setup-option-2-local-development-environment](https://reactjs.org/tutorial/tutorial.html#setup-option-2-local-development-environment)


With SVG
- [https://auth0.com/blog/developing-games-with-react-redux-and-svg-part-1/](https://auth0.com/blog/developing-games-with-react-redux-and-svg-part-1/)
- [https://medium.com/@ericschwartz7/using-react-with-svg-57958f16e68a](https://medium.com/@ericschwartz7/using-react-with-svg-57958f16e68a)

JSX to write HTML-like things in JS code
- `<script src="https://unpkg.com/babel-standalone@6/babel.min.js"></script>`
- Conversion with Babel

- [https://github.com/tanem/react-svg](https://github.com/tanem/react-svg)
    - This looks like it's for SVG files.

- [http://youmightnotneedjquery.com/](http://youmightnotneedjquery.com/)

js

```javascript
const e = React.createElement;

class LikeButton extends React.Component {
  constructor(props) {
    super(props);
    this.state = { liked: false };
  }

  render() {
    if (this.state.liked) {
      return 'You liked this.';
    }

    return e(
      'button',
      { onClick: () => this.setState({ liked: true }) },
      'Like'
    );
  }
}

ReactDOM.render(
    e(LikeButton),
    document.getElementById('root')
);
console.log('OK')
```

[https://reactjs.org/docs/add-react-to-a-website.html](https://reactjs.org/docs/add-react-to-a-website.html)

:

```
<svg width="100" height="100"　id="canvas">
<circle cx="50" cy="50" r="40" stroke="green" strokeWidth="4" fill="yellow" />
  </svg>
```



js

```javascript
  handleClick(e) {
    console.log("clicked");
    this.setState(prevState => {
      console.log(prevState);
      return {
        value: !prevState.value
      };
    });
  }

```


---
This page is auto-translated from [/nishio/React](https://scrapbox.io/nishio/React) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.