---
title: "Social Hack Day #64"
---

[Social Hack Day #64](https://www.notion.so/code4japan-community/Social-Hack-Day-64-c07a360e77ee4d539467b60dbc671196)
- [Broad Listening_SHD#64](https://code4japan-community.notion.site/_SHD-64-895211136a6a46d4aa57967cc513a913)

<img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/>The chat logs indicate that the Social Hack Day gathering included a trial of broad listening tools such as Polis and Talk to the City (TTTC) and related work and discussions. The main events and the know-how gained are summarized below.

Major events:.
- Polis and TTTC trial and description
- Attempt to run TTTC on Google Colab
- Prepare data and address related issues (encoding, NaN values, etc.)
- Discussion of how to display and publish results
- Discussion on how to manage FAQs

Reusable Know-how:.
- Polis use:.
    - Onboarding is easy because you can try it out as an administrator simply by registering an account.
    - It is effective to experience the voting side in the sample and then try the admin side.
- Using TTTC:.
    - Google Colab can be used to reduce the time and effort required to build the environment.
    - It is good to separate the analysis on your own data from the run on sample data.
    - Google Drive mounts are useful for persistence of results.
- TTTC Data Preparation:.
    - When outputting CSV from Excel, care must be taken with encoding and data type.
    - Try to save in UTF-8.
    - Determine in advance how to process NaN values.
- Error handling:.
    - Encoding-related errors can be checked and corrected with the appropriate editor (e.g., Cursor).
    - Errors due to LLM return format mismatches may be avoided by changing the model (e.g., from GPT-3.5 to GPT-4).
- Result publication:.
    - Easily publishable using GitHub Pages.
- Document Management:.
    - Choose a management location for information such as FAQs, taking accessibility and ease of updating into consideration.
    - A method of regularly transcribing Slack discussions into a structured document such as Notion is effective.
- Tutorial design:.
    - It is easier to understand if you explain basic operations on sample data and analysis on your own data separately.

These know-how may be useful for similar projects and technology implementation in the future. In particular, useful insights have been gained on how to prepare and explain the work to a team that includes non-engineers.

next time (occasion)
- [https://x.com/CodeforJapan/status/1839942622413992366](https://x.com/CodeforJapan/status/1839942622413992366)


--- chatting and stuff.

Save Point" concept to "save" projects that did not work out
- [The concept of "save points" to "save" projects that have gone wrong｜kaizumaki](https://note.com/kaizumaki/n/n7db132bd63d9)

- [[Social media should be maintained by taxpayers because communication is social infrastructure.]]

- [[foreign enemy]]

- [[Visualization of parameter swing trade-offs]]

[[Code for SAKE]]

[[Code for Japan Summit 2024]]

- [[The Tower]]

---
This page is auto-translated from [/nishio/Social Hack Day #64](https://scrapbox.io/nishio/Social Hack Day #64) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.