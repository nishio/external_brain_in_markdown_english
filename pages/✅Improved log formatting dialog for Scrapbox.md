---
title: "✅Improved log formatting dialog for Scrapbox"
---

from  [[✅ Make log sharing a dialog instead of opening it in a separate tab.]]
- It won't open in a separate tab.
    - Currently, the log formatting dialog for Scrapbox can only be accessed from the log display screen.
    - What should we do?
        - Opening a new tab unconditionally is still not a good idea.
        - Adding an open button to the dialog just adds one more click.
        - We did that and improved the flow of exporting for Scrapbox separately.
- There are issues that should take precedence over the one-click increase.
- There is a button below the large text area.
    - On an iPhone, the buttons are hidden by a virtual keyboard.
    - Move the ✅ button up
- Copy text, open Scrapbox, title and paste.
    - Obviously, it's a hassle.
    - ✅Add button to open Scrapbox with first remark as title
    - The text is also copied at this time, so you can just paste it.
    - Create pages directly with Scrapbox via API -> Don't
        - I did not want to pass the entire content to the API because it would have resulted in URL Too Long, even in a normal use case.
        - Content that is interrupted in the middle is more disturbing than nothing.
    - ✅Memorize the project name
        - Right now, the default project name is nishio, but users will of course want to use their own project
            - Do this as part of [Save ✅Keicho settings

Current Flow
- Conversation Mode→Share→Open in another tab→Open Scrapbox dialog→Open Scrapbox button


---
This page is auto-translated from [/nishio/✅Scrapboxむけのログ整形ダイアログ改善](https://scrapbox.io/nishio/✅Scrapboxむけのログ整形ダイアログ改善) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.