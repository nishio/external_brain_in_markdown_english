---
title: "I have a file in Azure Blob Storage but I can't see it in Storage Explorer"
---

[When versioning is disabled in Azure Blob Storage, the default value "Active BLOB" in Azure Storage Explorer appears to have no files.
- Azure Storage Explorer can be checked by setting the display filter to "All Blobs and Blobs without current version".
- <img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/>The Blob exists normally as a BlockBlob in the Hot Tier, but isCurrentVersion is set to None. This may be the cause.
- Once displayed, it was selected as an active BLOB, or it was then also displayed in the "active BLOB".


Added test tool to verify connection and basic upload to Azure Blob Storage - by nishio
[https://github.com/digitaldemocracy2030/kouchou-ai/pull/711](https://github.com/digitaldemocracy2030/kouchou-ai/pull/711)
![image](https://gyazo.com/81698c6fdf2532005c5b1cd5d9ac2298/thumb/1000)


---
This page is auto-translated from [/nishio/Azure Blob StorageにファイルがあるのにStorage Explorerで見えない](https://scrapbox.io/nishio/Azure Blob StorageにファイルがあるのにStorage Explorerで見えない) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.