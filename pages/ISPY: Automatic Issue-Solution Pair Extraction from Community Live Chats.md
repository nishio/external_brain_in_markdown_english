---
title: "ISPY: Automatic Issue-Solution Pair Extraction from Community Live Chats"
---

[[ISPY]]
[[Issue-Solution Pair]]
[https://arxiv.org/abs/2109.07055](https://arxiv.org/abs/2109.07055)

In this paper, we propose ISPY, a method for automatically extracting "issues" and "solutions" that developers encounter in live chats (e.g., Gitter) in OSS development communities. The main flow consists of the following three steps

1.### Disentanglement
.
- To automatically separate a miscellaneous sequence of statements into topics (dialogs). First, the existing model is used to split the chat history into multiple topic units.

2.### Issue Detection
.
- Determine if the beginning of each segmented dialog ("the first part posted by the speaker") describes an issue, using a combination of BERT-based embedding, textual CNN, local attention mechanism (Local Attention), and 15 heuristic attributes (such as negation and sentiment score). The combined features are input to classify with high accuracy whether an issue is stated or not.

3.### Solution Extraction
.
- Automatically extracts the statements that correspond to the solution from the rest of the dialog (the group of statements after the beginning) that has been determined to be an issue. As with issue detection, CNN and local attention mechanisms are used to group the selected utterances in chronological order to form a solution.

The experiment evaluated 8 OSS communities (750 dialogs in total / 171 of them with issues) and achieved F1 scores significantly higher than existing methods (76% for issue detection and 63% for solution extraction). We also showed an actual case where ISPY was applied to another community to resolve an unanswered question on Stack Overflow, and six cases were ultimately accepted as "best answers. These results indicate that ISPY can efficiently structure valuable knowledge (issues and their solutions) buried in chat history and reuse it on other Q&A sites and developer support tools.

private chat: [https://chatgpt.com/c/679b38d7-c3c0-8011-8107-c6ec2aeea8b3](https://chatgpt.com/c/679b38d7-c3c0-8011-8107-c6ec2aeea8b3)

---
This page is auto-translated from [/nishio/ISPY: Automatic Issue-Solution Pair Extraction from Community Live Chats](https://scrapbox.io/nishio/ISPY: Automatic Issue-Solution Pair Extraction from Community Live Chats) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.