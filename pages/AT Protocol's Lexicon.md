---
title: "AT Protocol's Lexicon"
---

[[Lexicon]] in [[AT Protocol]]
[Lexicon | AT Protocol](https://atproto.com/specs/lexicon)
<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>
- Lexicon is a schema definition language for describing atproto records, HTTP endpoints (XRPC), and event stream messages, and is based on the atproto data model.
- Lexicon is allowed to change over time
    - Some restrictions exist to ensure forward and backward compatibility. The basic principle is that old data must still be valid under the updated Lexicon and new data must still be valid under the old Lexicon.
    - New fields must be optional
    - Required fields cannot be deleted.
    - Type cannot be changed.
    - Field cannot be renamed.
    - If a larger, more disruptive change is required, a new Lexicon name must be used.
- Lexicon's authority is determined by the NSID and is rooted in DNS control of domain authority.
    - That authority has ultimate control of the Lexicon definition and is responsible for the maintenance and distribution of the Lexicon schema definition.
- Protocol implementations should consider data invalid to Lexicon as completely invalid and should not attempt to repair or partially process individual data.
    - Unexpected fields of data that do not follow Lexicon should be ignored. When validating the schema, they should be treated as worst case warnings. This is to allow for schema evolution by controlling authorities and to be robust in the case of older Lexicons.
- A possible future change might be a change in validation rules for unexpected additional fields. For example, there could be a mechanism to indicate that a schema is "closed" or rules around field name prefixes (x-) to indicate informal extensions.
---
This page is auto-translated from [/nishio/AT ProtocolのLexicon](https://scrapbox.io/nishio/AT ProtocolのLexicon) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.