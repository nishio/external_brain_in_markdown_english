---
title: "Running TTTC with Colab"
---

Trying to get [[Talk to the City]] to work with [Google Colab

[Talk to the City Scatter on Google Colab](https://colab.research.google.com/drive/1nY5ENhs559f6oKWMa0lqrfsA_1kTm0hd?usp=sharing)

Reboot required after pip install
- ![image](https://gyazo.com/8f77ea207b32f304ba45378e2dcfa95e/thumb/1000)
- Due to numpy installation
- I rebooted and re-ran from the top and it works.

The part where you put the OpenAI API key in the environment variable and the part where main.py asks for interactive operations is troublesome.


Put the OpenAI API key into an environment variable
- [kaggle - Setting environment variables in Google Colab - Stack Overflow](https://stackoverflow.com/questions/53306150/setting-environment-variables-in-google-colab)
py

```
import getpass, os
OPENAI_API_KEY = getpass.getpass("input OPENAI_API_KEY")
os.environ["OPENAI_API_KEY"] = OPENAI_API_KEY
```

- It's done.
    - It asks you interactively and you type it in.

main.py asks for interactive operations.
- <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>The tool I run in Google Colab asks me to Press Enter, what should I do?
- <img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>`!echo | <your_command_here>`
- I see. I got it.

execution (e.g. program)
- ![image](https://gyazo.com/a72c994b1f56b4bd9a6ceb1b6625ce7a/thumb/1000)
- > Pipeline completed.
- It's done.

How to preview the output static HTML
- Is it absurd to set up an HTTP server on Google Colab and preview it?
- Zip it up and have it downloaded?
    - ![image](https://gyazo.com/9c8b3f803e9b903dbd84b87fafd7b13a/thumb/1000)
    - Even if I download it, I'll have to set up a local HTTP server to see it after all...


TTTC2024-08-20
[[Cybozu Lab Youth Summer Camp 2024]]

---
This page is auto-translated from [/nishio/TTTCをColabで動かす](https://scrapbox.io/nishio/TTTCをColabで動かす) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.