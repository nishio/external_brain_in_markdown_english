---
title: "Building an Environment for Talk to the City"
---

Building an environment for [Talk to the City
It's in the README [https://github.com/AIObjectives/talk-to-the-city-reports/tree/main/scatter](https://github.com/AIObjectives/talk-to-the-city-reports/tree/main/scatter)

`$ cd scatter`
`$ python3 -mvenv venv`
`$ . venv/bin/activate`
`$ pip install -r requirements.txt `


The following is not organized
- Rough notes as of 6/23
    - I feel like I'm stepping in all kinds of trouble if I don't get to Python 3.10.
    - The difficulty of building this environment is an obstacle to the spread of digital democracy and should be resolved (it is preferable that a diverse range of citizens can use this tool).





# Trouble with Python 3.11
.
The README contains
> We recommend to use python 3.10+ and install the dependencies as follows:
but Python 3.11 will eliminate distutils, so I'll rub it in here.

`$ pip install --upgrade pip setuptools`
as a result of

I modified some of the requirements.txt and it worked.
:

```
numpy>=1.25.2
tiktoken>=0.5.1
```



# continued
`$ python -c "import nltk; nltk.download('stopwords')"`

`$ cd next-app`
`$ npm install`

Since vulnerabilities are detected here
`$ npm audit fix --force`
You can also do

# try it
`$ cd pipeline`
- I just did `cd next-app`, so `cd ... /pipeline`.
`$ export OPENAI_API_KEY = sk-...`
- Of course, you need a real KEY.
- Aren't there some environments where you can't have a space before or after `=`?
`$ python main.py configs/example-polis.json`

# Trouble with Python 3.11
.
I heard that tenacity is not 3.11 compliant?
[https://github.com/langchain-ai/langchain/issues/22972](https://github.com/langchain-ai/langchain/issues/22972)
8.4.0 would give me an error.
pip install tenacity==8.1.0

This langchain freshly made bug!

---
This page is auto-translated from [/nishio/Talk to the Cityの環境構築](https://scrapbox.io/nishio/Talk to the Cityの環境構築) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.