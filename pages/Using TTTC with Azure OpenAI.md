---
title: "Using TTTC with Azure OpenAI"
---

For various reasons, we decided to use [[Azure OpenAI Service]] instead of OpenAI's API for Talk to the City.
- [Azure OpenAI Service - Advanced Language Models | Microsoft Azure](https://azure.microsoft.com/ja-jp/products/ai-services/openai-service)

[[Talk to the City]] Scatter hard-codes LangChain's ChatOpenAI
extraction.py

```
llm = ChatOpenAI(model_name=model, temperature=0.0)
```


So to use it in [[Azure OpenAI]], we need to rewrite here

The original code imports `from langchain.chat_models import ChatOpenAI`.
I think it would work easily if you think about it `from langchain.chat_models import AzureChatOpenAI`, don't you?
- The expectation is that LangChain is tucked in as a middle layer to abstract the lower layers.
- But somehow it didn't work.
    - We haven't identified the cause, so it's possible this isn't the problem here.
I finally got it to work `from langchain_openai import AzureChatOpenAI`.

Here's what the modifications look like
py

```
# llm = ChatOpenAI(model_name=model, temperature=0.0)
llm = AzureChatOpenAI(
    model_name=model, 
    temperature=0.0,
    azure_endpoint=os.getenv("AZURE_OPENAI_ENDPOINT"),
    openai_api_key=os.getenv("AZURE_OPENAI_API_KEY"),
    openai_api_version=os.getenv("AZURE_OPENAI_API_VERSION"))
```

I'm reading `.env` in dotenv for more parameters.
py

```
import dotenv
import os
dotenv.load_dotenv()
```

Information such as `AZURE_OPENAI_ENDPOINT` to be written in `.env` can be found by creating a "resource" and deploying a "model".
![image](https://gyazo.com/65f74e64e4b97696fd5abe034c27e721/thumb/1000)
![image](https://gyazo.com/0eb102394a58bfdb35d4d1108a4fbe8f/thumb/1000)
![image](https://gyazo.com/23a267e6425dd5da9279dcc21b62d6c6/thumb/1000)

I thought AZURE_OPENAI_API_VERSION was necessary, but it is loaded in the query parameter of AZURE_OPENAI_ENDPOINT, so it might be OK to omit it.

Also, I thought this would be enough, but Embedding is a separate model, so I need to work on that as well.
`from langchain_openai import AzureOpenAIEmbeddings`
py

```
embeds = AzureOpenAIEmbeddings(
    model="text-embedding-3-large",
    openai_api_key=os.getenv("AZURE_OPENAI_API_KEY"),
    openai_api_version=os.getenv("AZURE_OPENAI_API_VERSION")
).embed_documents(args)
```

Why is there no AZURE_OPENAI_ENDPOINT over here?
- Oh, you're reading `AZURE_EMBEDDING_ENDPOINT` directly from the environment variable.
    - In `.env` it says something like `AZURE_EMBEDDING_ENDPOINT=https://<resource>.openai.azure.com/openai/deployments/text-embedding-3-large/embeddings?api- version=2023-05-15` or something like that.


[[In-house TTTC]]

---
This page is auto-translated from [/nishio/TTTCをAzure OpenAIで使う](https://scrapbox.io/nishio/TTTCをAzure OpenAIで使う) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.