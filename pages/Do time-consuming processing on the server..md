---
title: "Do time-consuming processing on the server."
---

I've been doing some preliminary research, but a team member made it quick and easy, so I guess I'd better read that implementation.

<img src='https://scrapbox.io/api/pages/nishio-en/o3-mini-high/icon' alt='o3-mini-high.icon' height="19.5"/>
- Requirement:
    - After uploading the CSV to the server, a Python script will perform the analysis process, which takes about 30 minutes, and build a mechanism to return the results.

- Initial study:
    - Consider an approach that uses asynchronous jobs (Celery, RQ, etc.) for long-time processing.

- Design in GCP:
    - Save CSV files to Cloud Storage
    - Create asynchronous tasks in Cloud Tasks and process them with a dedicated service on Cloud Run
    - Analysis results are stored in Cloud Storage (or DB) and users are notified of the results

- Implementation example:
- Using Flask, create a CSV upload endpoint and a processing endpoint for invocation from Cloud Tasks.
- Sample code, Dockerfile, requirements.txt, and deployment instructions.

The goal is to use managed services in this process to design a system that is scalable and has a low operational load.

[https://chatgpt.com/c/67a46e96-b420-8011-92e5-8e6611c860b9](https://chatgpt.com/c/67a46e96-b420-8011-92e5-8e6611c860b9)

---
This page is auto-translated from [/nishio/時間のかかる処理をサーバでやる](https://scrapbox.io/nishio/時間のかかる処理をサーバでやる) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.