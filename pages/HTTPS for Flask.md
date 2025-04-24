---
title: "HTTPS for Flask"
---

Answered Dec 5 '20 by Mark Dominus
python

```
import ssl
context = ssl.SSLContext()
context.load_cert_chain('fullchain.pem', 'privkey.pem')
...
app.run(…, ssl_context=context)
```

'fullchain.pem', 'privkey.pem' are created by [LetsEncrypt Certbot

[rest - can you add HTTPS functionality to a python flask web server? - Stack Overflow](https://stackoverflow.com/questions/29458548/can-you-add-https-functionality-to-a-python-flask-web-server)
[[Flask]] [[HTTPS]]

`$ flask run --cert fullchain.pem --key privkey.pem`
[python - Run Flask dev server over HTTPS using CLI - Stack Overflow](https://stackoverflow.com/questions/48467835/run-flask-dev-server-over-https-using-cli)

---
This page is auto-translated from [/nishio/FlaskのHTTPS化](https://scrapbox.io/nishio/FlaskのHTTPS化) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.