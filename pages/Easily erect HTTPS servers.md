---
title: "Easily erect HTTPS servers"
---

Something I looked into in the thought process of building a local HTTPS server and embedding various services in iframes to make it dashboard-like.
- Result: [[Embed HTTPS services into other HTTPS services]] I didn't try it because I gave up when I found that some services are blocked in the header.


<img src='https://scrapbox.io/api/pages/nishio-en/o3-mini-high/icon' alt='o3-mini-high.icon' height="19.5"/>
- mkcert and [[Caddy]] were introduced as a way to build a local HTTPS server.
- Caddy automatically obtains HTTPS certificates (such as Let's Encrypt) and can be configured with a simple Caddyfile.
- As an example of a setup for delivering static content locally,
:

```
https://localhost {
 root * ./public
  file_server
 }
```

- and how to start the server with `caddy run`.

[https://chatgpt.com/c/67bf3ea3-eea0-8011-9939-626e8039770f](https://chatgpt.com/c/67bf3ea3-eea0-8011-9939-626e8039770f)

[Install — Caddy Documentation](https://caddyserver.com/docs/install)

---
This page is auto-translated from [/nishio/HTTPSサーバを手軽に建てる](https://scrapbox.io/nishio/HTTPSサーバを手軽に建てる) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.