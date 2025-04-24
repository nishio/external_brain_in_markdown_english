---
title: "Flask-CORS"
---

When I set up a server with Flask to experiment with experimental functions, the server's API is blocked by the CORS policy when I try to read the JS of the content placed on another server.

:

```
Access to fetch at 'http://localhost:5000/api/' from origin 'http://localhost:3000' has been blocked by CORS policy: Response to preflight request doesn't pass access control check: No 'Access-Control-Allow-Origin' header is present on the requested resource. If an opaque response serves your needs, set the request's mode to 'no-cors' to fetch the resource with CORS disabled.
```


server-side
- Use [[Flask]]-[[CORS]] (`pip install -U flask-cors`)
    - [https://flask-cors.readthedocs.io/en/latest/](https://flask-cors.readthedocs.io/en/latest/)
diff

```
  from flask import Flask
+ from flask_cors import CORS

  app = Flask(__name__)
+ CORS(app)
```


client-side
diff

```
  fetch("http://localhost:5000/api/", {
+  mode: "cors",
   method: "POST",
    body: JSON.stringify(data),
    headers: {
      "Content-Type": "application/json",
    },
  }).then((response) => {
```


Flask receives the data as json since it is hit with "Content-Type": "application/json".
- I forgot to do this and got a 400 Bad Request.
    - [[400 Bad Request by hitting Flask from JS]]

[[preflight request is 308 Permanent Redirect]] in OPTIONS
- Caused by trailing slash
---
This page is auto-translated from [/nishio/Flask-CORS](https://scrapbox.io/nishio/Flask-CORS) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.