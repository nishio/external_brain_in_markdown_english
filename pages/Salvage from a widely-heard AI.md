---
title: "Salvage from a widely-heard AI"
---

2025-03-27
When I put large data in the Azure environment's broadband AI, it ran for a while and then gave me an error.
I want to retrieve intermediate data in Azure Container App to find out what caused the failure.
![image](https://gyazo.com/7f58f3e0d85f1b677e529026b56f4eb8/thumb/1000)

Note: The
- The script [https://github.com/digitaldemocracy2030/kouchou-ai/blob/main/scripts/fetch_reports.py](https://github.com/digitaldemocracy2030/kouchou-ai/blob/main/scripts/fetch_reports.py) to retrieve data from a successful report was created on 3/25.
- This time we are talking about extracting intermediate data, a task that is not necessary for most people.
- o3 is a memo that forces you to hack a troublesome situation that says "<img src='https://scrapbox.io/api/pages/nishio-en/o3-mini-high/icon' alt='o3-mini-high.icon' height="19.5"/>If you are in an Azure environment, uploading to [[Azure Blob Storage]] is the only realistic way to do it"!
- While this is being done, the admin and results display screens will of course all stop working.
- It's something that wouldn't be possible for a normal 24-hour web service operation, but in this case we're doing it because we're not in a situation where we're providing a 24-hour service for our customers.

## bash into container
.
:

```
az containerapp exec \
  --name <container app name> \c
  --resource-group <resource group name> }
  --container <container name> \cHTML
  --command "/bin/bash"
```



## zip and serve with port=8001
.
`$ apt update`
`$ apt install zip`
`$ cd broadlistening/pipeline`
`$ zip -r outputs.zip outputs`
`$ python -mhttp.server 8001`


## Temporarily change the ingress settings on the api server
.
API server returns `{"status": "ok"}` when accessed with HTTPS as usual
This is Azure forwarding the request to an HTTP server running on 8000
Temporarily change this setting to 8001.

![image](https://gyazo.com/44c170eaf8c7121a86c335f0c8e5708a/thumb/1000)![image](https://gyazo.com/fb6776b7b932f9b01ef6737d327decf8/thumb/1000)

Now when you access the API server, you will see the results.zip file you just created and be able to download it.
![image](https://gyazo.com/0b3066753a9f09a68b6acddbaef31a5e/thumb/1000)

Don't forget to put it back when you're done downloading.

## aside: see results
.
![image](https://gyazo.com/4b04de66ecbc24d92239439361f8420c/thumb/1000)![image](https://gyazo.com/14a017fe6449b073fd8a33ac264f0f53/thumb/1000)
A normal successful report would look like the one on the left, but this one is on the right
25000~ data of 5.2MB of extraction results are output to args.csv.
I think it might be "Out of Memory", but I think it might be so.

I'm using text-embedding-3-small with embedding and it's a float32 with 1536 dimensions per case.
I'm handling that with Python's `list[float]`.
Python's float is 8 bytes in double precision float64, so total = 1536 × 8 = 12,288 bytes (about 12 KB)
25,000 records would be roughly 300 MB.
I guess a container with 1GB of memory means there's not that much room for applications.
2GB should be more than enough.
---
This page is auto-translated from [/nishio/広聴AIからのサルベージ](https://scrapbox.io/nishio/広聴AIからのサルベージ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.