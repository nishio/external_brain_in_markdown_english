---
title: "Flask to HTTPS"
---

There are cases where you want HTTPS to speak to the development at hand.
I looked up how to do it.
During local development, [[webpack-dev-server]] was also HTTP, so it was an afterthought.
(I was too quick to assume that the error was due to another cause.)
- [[HTTPS for Flask]]

memo

`$ openssl genrsa -aes128 1024 > server.key`
`$ openssl req -new -key server.key > server.csr`
CSR: Certificate Signing Request
`$ openssl x509 -in server.csr -days 365 -req -signkey server.key > server.crt`
CRT: Certificate
`$ flask run --cert server.crt --key server.key`
: 

```
 * Serving Flask app "server" (lazy loading)
 * Environment: development
 * Debug mode: on
 * Running on https://127.0.0.1:5000/ (Press CTRL+C to quit)
 * Restarting with stat
 * Debugger is active!
 * Debugger PIN: xxx-xxx-xxx
Enter PEM pass phrase:
```

I can make it HTTPS with this, but it seems better to make it without passphrase, because I'm asked for passphrase every time I auto-restart after editing the code, I'll try it next time I need it.

memo
[Create error-free self certification authority & server certificates in Chrome - run and climb](https://blog.liclab.com/2018-02-07/celf-signed-certificate/)
---
This page is auto-translated from [/nishio/FlaskをHTTPSにする](https://scrapbox.io/nishio/FlaskをHTTPSにする) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.