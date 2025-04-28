---
title: "Devin credit used up 4/27"
---

from  [[Diary 2025-04-27]]
Devin credit used up
216.68 ACUs
I've got an idea for you to consume your remaining credits.
> [https://github.com/nishio/external_brain_in_markdown](https://github.com/nishio/external_brain_in_markdown) this is the author's external brain
>  Please read this and find "ideas you think should be implemented but haven't started yet" and indicate them in a numbered list format.
It wasn't good.
- I picked up the FUTURE WORK on the paper's notes.

Well, there are a lot of projects themselves that I'd like to move forward with.
- Like Kozaneba.
- AIPM, for example.
It doesn't fall into the form of an easily executable task.
- And the part about making it a task involves a high level of decision making, so it's not something you can just throw at Devin.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I have 40 extra Devin tokens and they expire today, what should I do?
<img src='https://scrapbox.io/api/pages/nishio-en/o3/icon' alt='o3.icon' height="19.5"/>
- ✅ Static analysis of entire code & refactor proposal
- ✅ Automatic generation/updating of README and function comments
- ✅ Automatic test case generation (e.g., TestGen-LLM-style)
- Create outputs for "read later"
    - Examples: archi-diagrams of the entire technology stack, dependency graphs, vulnerability reports, improvement roadmaps...
    - The generated material can be saved as Markdown/HTML/PDF for use even after the token expires.

Kozaneba
- [https://app.devin.ai/sessions/f20984a03b224d228b288e0e4244129f](https://app.devin.ai/sessions/f20984a03b224d228b288e0e4244129f)
- [https://app.devin.ai/sessions/40113237620548d9b7af6359dc360cb2](https://app.devin.ai/sessions/40113237620548d9b7af6359dc360cb2)
- Fixed an issue that does not work on iPad
    - [https://app.devin.ai/sessions/1a484adb43ae45c1ac2da066c4171528](https://app.devin.ai/sessions/1a484adb43ae45c1ac2da066c4171528)
- [https://app.devin.ai/sessions/84544e87ab7c4dc2bcfdf7712bcfd2ec](https://app.devin.ai/sessions/84544e87ab7c4dc2bcfdf7712bcfd2ec)
- Oh, I got two bug reports on Kozaneba.
    - I wasn't aware of it.
    - Let's throw it to Devin in a messy way.
    - How dare they both say "fixed".
AIPM
- [https://app.devin.ai/sessions/bc016a2e8e8e4c65968c898993152e49](https://app.devin.ai/sessions/bc016a2e8e8e4c65968c898993152e49)
Where is keicho's code?
- I looked at netlify, looked at github, and realized it's just the front end.
- not even in vercel
- It was heroku.
- > The Heroku-20 stack is deprecated
- >  This app is using the Heroku-20 stack, which is deprecated. From April 30th, 2025, Heroku-20 will be end-of-life and no longer receive security updates. From May 1st, 2025, builds will be disabled. Please upgrade your app to a newer Heroku stack.
- Wow, I was pushing to the git of heroku itself, so there's only code locally and in heroku, that's how it works.
    - Let's create a private repo on GitHub and push it.
- It's a sign of the times.
    - At that time, the number of private repos on GitHub was limited, and I was mainly using bitbucket, which was unlimited, probably.
    - CUI version of keicho bot is on bitbucket before WebUI was available.
        - bitbucketHow do I log in, oh well (...)
[http://www.teratti.jp/heart/hew/download/index.htm#h_develop](http://www.teratti.jp/heart/hew/download/index.htm#h_develop)
- I remember the old software connection.
    - I don't know how they kept the site up, it's been years.
    - Delphi code created 25 years ago
    - The source code is not even a ZIP, it's an LZH.

Kozaneba's development is amazing.
- It seems to have been fixed just by throwing user bug reports as is.
- Have them read the code and report on improvements and make them issue.
- Choose the one that looks good in the issue and let it run.
    - If the issue is too big, I say take it apart.
- The ones that CI's go through don't care and merge.

Says he wants to refactor Keichobot.
- Cover it with a test, I say.
    - mecab says it's rubbing off.
    - ask o3 and pass on
    - > Updated mecab-python3 version from 0.996.5 to >=1.0.9 for compatibility with Python 3.12.


<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>What is causing Netlify deployment checks to fail?
<img src='https://scrapbox.io/api/pages/nishio-en/devin/icon' alt='devin.icon' height="19.5"/>Netlify deployment failure is due to a version conflict between the reactn package and @types/react. reactn requires @types/react@^16.8.0, but the project is @types/react@17.0.52を使用しています. I have added the .npmrc and netlify.toml files to resolve this issue, but may need additional permissions on the Netlify configuration.
<img src='https://scrapbox.io/api/pages/nishio-en/o3/icon' alt='o3.icon' height="19.5"/>To summarize, Netlify's npm v7 or later treats "peerDependencies conflict" as an error,
The @types/react@^16.8.0 required by reactn conflicts with your project's @types/react@17.x and stops the installation. It's a typical pattern that local installations are only allowed because they use npm v6 or earlier and stop with a warning. ...
<img src='https://scrapbox.io/api/pages/nishio-en/devin/icon' alt='devin.icon' height="19.5"/>We will try the cleanest of the suggested methods, "A. Align dependencies" approach: update reactn to the latest version 2.2.6, regenerate package-lock.json, and redeploy. We will keep you posted on our progress.


I went to bed and woke up.
- We were able to use up the ACUs that were about to expire without incident!
- And right after that it switched to pay-as-you-go mode.

---
This page is auto-translated from [/nishio/Devinクレジット使い切り4/27](https://scrapbox.io/nishio/Devinクレジット使い切り4/27) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.