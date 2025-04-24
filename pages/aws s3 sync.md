---
title: "aws s3 sync"
---

When syncing from hand to S3, if --delete is not added, the data on S3 will not be deleted even if it disappears on hand.
- [sync — AWS CLI 1.16.266 Command Reference](https://docs.aws.amazon.com/cli/latest/reference/s3/sync.html)

If --exaxt-timestamp is not attached, files with the same file size are considered unchanged

---
This page is auto-translated from [/nishio/aws s3 sync](https://scrapbox.io/nishio/aws s3 sync) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.