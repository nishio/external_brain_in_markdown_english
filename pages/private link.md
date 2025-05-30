---
title: "private link"
---

- [[Notes on Scrapbox extensions I would like to make]]

use case
- Place files that cannot be published for copyright or other reasons (articles, cut and scanned books) in Dropbox, etc.
- Write a link to it in Scrapbox.
- Write comments, etc. on the file.
- I want to open a link with one click, others should not.

Mounting plan 1
- Set the key to the extension.
- If you write `[secret URL]`, the extension encrypts the URL part and writes it to Scrapbox.
- Third parties viewing the public project cannot follow the link because it is encrypted.
- When displayed, that URL portion is decrypted, and the user who has the extension can use it as if it were just a link.
    - If I put it in the UserScript, the decryption key will be exposed, no?
    - Can I use localStorage?

Mounting plan 2
- I didn't want to have a separate database, so I was thinking of having all the information to decrypt the original URL in the URL section.
    - But wait, what?
    - You can get row data at `https://scrapbox.io/api/pages/<privateProj>/<pageName>`.
    - You could write a correspondence table in Private Project.

visually pleasing design
- `[link to secret description page? Information for restoring original URL]`
    - People who don't have the extension can also understand that it's a link they can't follow because they don't have the extension.

Input Method Proposal
- Copy the URL, convert it in Automator and paste it
- Confidential information does not get out.

---
This page is auto-translated from [/nishio/プライベートリンク](https://scrapbox.io/nishio/プライベートリンク) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.