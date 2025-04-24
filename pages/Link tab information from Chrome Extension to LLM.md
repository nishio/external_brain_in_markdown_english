---
title: "Link tab information from Chrome Extension to LLM"
---

<img src='https://scrapbox.io/api/pages/nishio-en/o1 Pro/icon' alt='o1 Pro.icon' height="19.5"/>
The following is the general flow of writing information about open tabs from the Chrome extension to the file system and passing it to the LLM.

1.### Authorization Settings
.
    - Use the `tabs` permission to get information about open tabs.
        - For Manifest V3, add `"tabs"` to `permissions`.

2.### Get tab information
.
    - Get URL, title, etc. with `chrome.tabs.query({})` etc.

3.### file write
.
    - Since it is difficult for the Chrome extension to write directly to local files, one of the following methods is used.
        - via backend: POST to server via XMLHttpRequest/fetch and write to a file on the server side.
            - File System Access API: Involves user interaction, but allows access to files from the browser (note support status).
        - storage API: Temporarily stored in `chrome.storage.local`, etc., and retrieved and filed by another mechanism.

4.### input to LLM
.
    - Tab information (URL, title, text, etc.) saved to a file is read as LLM input.
        - If you run LLM locally, process files directly; if via Web API, send text data as a request.

The point is that Chrome extensions are restricted from writing directly to local files for security reasons, so they usually use the server or storage API. The tab information acquired in this way can be output as a summary and input into LLM to make it easier to understand the situation.
---
This page is auto-translated from [/nishio/Chrome拡張からLLMへタブ情報を連携](https://scrapbox.io/nishio/Chrome拡張からLLMへタブ情報を連携) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.