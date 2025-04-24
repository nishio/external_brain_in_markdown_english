---
title: "Exclude some tests with pytest"
---

I wanted to exclude execution of only tests that use server connections.

Mark only tests that use server connections with decorators (`server` in `mark.server` can be determined freely).
python

```
@pytest.mark.server
def test_server_io():
	...
```


The -m option at runtime can be used to specify marks to be executed, and logical operations such as not can be used for this.
`$ pytest -m "not server"`

[[pytest]]  [[software testing]]

---
This page is auto-translated from [/nishio/pytestで一部のテストを除外](https://scrapbox.io/nishio/pytestで一部のテストを除外) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.