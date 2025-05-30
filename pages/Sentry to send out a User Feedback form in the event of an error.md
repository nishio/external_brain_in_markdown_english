---
title: "Sentry to send out a User Feedback form in the event of an error"
---

from [[Sentry Memo]]
[[Sentry]] User Feedback
![image](https://gyazo.com/acaeefbdd92094f9ebfebfc4fb086cb4/thumb/1000)
- [React Error Boundary for React | Sentry Documentation](https://docs.sentry.io/platforms/javascript/guides/react/components/errorboundary/)
    - [User Feedback for React | Sentry Documentation](https://docs.sentry.io/platforms/javascript/guides/react/enriching-events/user-feedback/)
    - Tell the user when an error occurs.
        - Just an error message on the console doesn't get the message across.
    - There's a preset dialog that tells you when there's an error and collects feedback from the user.
        - Can we get this out?
        - I don't expect the user to write it down, but if I'm using it, I can send what I'm doing and what happened from here, and that can be read on Sentry's server, along with the stack trace and so on.
    - Create and try menus that intentionally generate errors.
    - `<Sentry.ErrorBoundary fallback="An error has occurred" showDialog>`
        - In development, I get a React error screen, and when I turn it off, I get the original screen; in production, I get nothing.
    - Hook and display before sending on your own
ts

```typescript
Sentry.init({...
  beforeSend(event, hint) {
    // Check if it is an exception, and if so, show the report dialog
    if (event.exception) {
      Sentry.showReportDialog({ eventId: event.event_id });
    }
    return event;
  },
});
```

        - In develop, there's a feedback screen below the error screen.
            - I'm getting a duplicate ID warning.
            - There are two feedback screens out there to begin with.
            - I thought it was a duplicate of showDialog, but turning it off doesn't change it.
            - Two errors with different error IDs or time stamps
                - Contents are the same
                - The event count display on the Sentry is also increasing by 2.
            - Does the error boundary cause it to come up twice? I thought so, but it has nothing to do with whether or not
            - →I decided to do the process on my own to display only once.

consideration
- Regarding errors that occur in the event handler when a menu item is selected, are they not caught by the error boundary, etc.?
    - something like that
    - [https://ja.reactjs.org/docs/error-boundaries.html](https://ja.reactjs.org/docs/error-boundaries.html)
    - > error boundary is a React component that catches JavaScript errors in its own child component tree, logs the error, and displays a fallback UI in place of the crashed component tree.
    - > error boundary does not catch the following errors
        - >  Event Handler (detail)
        - >  Asynchronous code (e.g., setTimeout or requestAnimationFrame callbacks)
- Why leave twice?
    - I wonder if React catches it once and then re-throws it.

---
This page is auto-translated from [/nishio/Sentryでエラー時にUser Feedbackのフォームを出す](https://scrapbox.io/nishio/Sentryでエラー時にUser Feedbackのフォームを出す) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.