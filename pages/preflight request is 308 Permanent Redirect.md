---
title: "preflight request is 308 Permanent Redirect"
---

> Access to fetch at '[http://localhost:5000/api/web/create'](http://localhost:5000/api/web/create') from origin '[http://localhost:3000'](http://localhost:3000') has been blocked by CORS policy: Response to preflight request doesn't pass access control check: Redirect is not allowed for a preflight request.

[Origin-to-Origin Resource Sharing (CORS) - HTTP | MDN](https://developer.mozilla.org/ja/docs/Web/HTTP/CORS)
[Preflight request - MDN Web Docs Glossary: Definition of web-related terms | MDN](https://developer.mozilla.org/ja/docs/Glossary/Preflight_request)

The browser precedes the request with the OPTIONS method.
The server is returning a 308 Permanent Redirect for the request and is therefore not considered CORSable.

cause
- Server side
    - `@app.route('/api/web/create/', methods=["GET"])`
- client-side
    - `fetch(APIROOT + "web/create", {...})`
- So this is redirecting access without the trailing slash to a URL with one.

solution
- `fetch(APIROOT + "web/create/", {...}) I just did `and it solved the problem.

[[CORS]]
[[Flask-CORS]]

---
This page is auto-translated from [/nishio/preflight requestが308 Permanent Redirect](https://scrapbox.io/nishio/preflight requestが308 Permanent Redirect) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.