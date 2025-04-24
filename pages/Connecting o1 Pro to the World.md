---
title: "Connecting o1 Pro to the World"
---

I had o1 Pro write an adapter to connect [[o1 Pro]] to the world, but when I posted the image in the middle, I couldn't share the log.
Link for self: [https://chatgpt.com/c/6752f412-c08c-8011-b98e-33728de871a4](https://chatgpt.com/c/6752f412-c08c-8011-b98e-33728de871a4)

<img src='https://scrapbox.io/api/pages/nishio-en/o1 Pro/icon' alt='o1 Pro.icon' height="19.5"/>The following is a brief summary to explain the process so far to a third party.
Summary: The
- MVP Construction:.
    - Create a Node.js script called tool_actions.js to provide a foundation for automatically operating the project by receiving instructions in JSON format (file edit, commit, test execution, etc.).
- In-browser AI utilization concept:.
    - Browser automation with Playwright, etc., and aimed to log in to AI services, submit instructions, and obtain results, but Cloudflare's human judgment and element manipulation were difficult, so another approach was considered.
- Conversion to Tampermonkey script:.
    - Tampermonkey is installed in Chrome, which is normally used, and a custom button (automation on/off) is added on the AI service page with a user script.
    - In an environment where page elements are loaded dynamically, detect when AI generation is complete (stop streaming or display a specific button) by making full use of waitForElement function, MutationObserver, etc.
- Clipboard manipulation and visualization:.
    - After generation is complete, the button for copying is automatically clicked, and the clipboard contents are retrieved and displayed by navigator.clipboard.readText(), enabling the actual processing flow to be confirmed.

Through the above process, we are attempting to build and verify a flow of MVP for the work cycle of automatic command input, result acquisition, and processing reflection to the AI service on the browser.


---
This page is auto-translated from [/nishio/o1 Proを世界に接続する](https://scrapbox.io/nishio/o1 Proを世界に接続する) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.