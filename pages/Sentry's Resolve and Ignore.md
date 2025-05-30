---
title: "Sentry's Resolve and Ignore"
---

Resolve will be flagged as resolved.
- Temporarily disappears from "Unresolved Issues".
- The flag returns when the same error occurs again.
- It appears again.
Ignore is flagged as IGNORED.
- Permanently disappears from "Unresolved Issues."
- Not displayed unless explicitly searched for.

In other words, if an error is reported and it is (or is supposed to be) fixed, it will be resolved. If it is not fixed, it will appear again.
Ignore can be used when an error is reported to Sentry but there is no need to fix it, but if it is a report that is not needed, shouldn't we fix it so that it is not reported in the first place?

> Resolve resolves immediately, and unresolves if it happens again. Ignore supresses alerts for the issue and hides it from the issue stream unless is:ignored is explicitly searched for. Delete deletes all data associated with the issue and creates a new issue if it happens again.
[https://forum.sentry.io/t/what-do-to-default-resolve-ignore-delete-buttons-do/8573](https://forum.sentry.io/t/what-do-to-default-resolve-ignore-delete-buttons-do/8573)

[[Sentry]]

---
This page is auto-translated from [/nishio/SentryのResolveとIgnore](https://scrapbox.io/nishio/SentryのResolveとIgnore) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.