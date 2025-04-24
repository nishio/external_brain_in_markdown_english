---
title: "pHiroshi AI2025-03-31~"
---

prev  [[pHiroshi AI2025-03-13~]]

2025-03-31
Previously, we were able to put the AI into our Azure environment, and now that we've announced it, we're ready to move on.

Where I'm concerned
- Instance created with Azure AI Foundary in the process of cleaning up and installing? I deleted the
    - Inadvertent collateral damage when deleting old resource groups
    - The setup for this area isn't actually included in the Makefile.
- It must have stopped working because I turned it off! I was in a hurry, but now it is working for some reason!
    - Is what you deleted left in place for a while in preparation for Undo?
    - Even if that's the case, it should be an error, because even if you get GC'd and realize it's stuck, it's too late, right?

In the process of developing the environment for internal use, should we separate the environment for deployment work and the environment for new feature development? I think it is a good idea.
- Should I separate the working folders or just separate them by branch?

Let's create a new environment to experience the feelings of newly joined developers.

Rename environment for deployment work
`$ mv kouchou-ai cybozu-kouchou-ai`

Check out the new kouchou-ai and name it kouchou-ai-dev
- I was Forking in the first place. [https://github.com/nishio/kouchou-ai](https://github.com/nishio/kouchou-ai)
    - Sync Fork
- Do a local git clone git@github.com:nishio/kouchou-ai.git kouchou-ai-dev

Start up locally with kouchou-ai-dev
- Edit .env
    - You've changed a lot.
    - > # Set production or development; if production, UI such as openapi will not be displayed.
    - > ENVIRONMENT=development
    - what is this?
- At first, I configured Azure Endpoint.
    - but in general people here are anxious about how much money they will be asked to put in the OpenAI API key.
        - With intermediate data export, you can say, "You can place this, and you can do it for free.
    - As for me, well, let's give it a shot.
- Download Sample Data
    - Last time it was 50 cases, this time 400.
    - Let's call it Sample400.
- execution (e.g. program)
    - ERROR:root:Task <Future at 0xffff6a09e0f0 state=finished raised AssertionError> failed with error:
    - Oh, no!
    - Or use OpenAI to isolate the problem.
    - Ah, it's done.
    - calling attention

Putting development aside for a moment, I thought that the missing instance of Azure AI Foundary must not be working properly, right? Let's solve it!
- [[Azure OpenAI Service]]
:

```
# Create Azure OpenAI Service resource
az cognitiveservices account create \
  --name kouchou-ai-openai \
  --resource-group nishio-kouchou-ai-rg \
  --kind OpenAI \
  --sku s0 \
  --location japaneast
  
# Get key
az cognitiveservices account keys list \
  --name kouchou-ai-openai \
  --resource-group nishio-kouchou-ai-rg

# Get endpoints
az cognitiveservices account show \
  --name kouchou-ai-openai \
  --resource-group nishio-kouchou-ai-rg \
  --query properties.endpoint
```


Change the settings and try to redeploy.
- Before that, change the .env in the development environment and re-test.
- No good, huh?

Uh, okay.
- First, it's asserting that "is it properly configured for Azure OpenAI Service?", but it's catching it upstream and determining that it's a failed API call.
    - When embedding, it goes straight out, but only ChatCompletion is caught.
        - It's not right to check the settings on the call in the first place.
- PR: [https://github.com/digitaldemocracy2030/kouchou-ai/pull/208](https://github.com/digitaldemocracy2030/kouchou-ai/pull/208)


<img src='https://scrapbox.io/api/pages/nishio-en/Devin/icon' alt='Devin.icon' height="19.5"/>
To update your Azure deployment to the latest version, perform the following steps
First, update the local repository to the latest state:
`$ git pull`
Log in to Azure:
`$ make azure-login`
To update an existing Azure environment, execute the following commands in this order
- a. Build the latest container image:
    - `$ make azure-build`
- b. Push the built image to Azure Container Registry:
    - `$ make azure-push`
    - First azure-acr-login-auto is required
- c. Update environment variables (if necessary):
    - `$ make azure-config-update`
- d. Modify the environment variables, especially in the administration panel (client-admin), and build:
    - `$ make azure-fix-client-admin`
- Verify that the deployment has completed successfully:
    - `$ make azure-verify`
    - `$ make azure-info`
These commands are defined in the Makefile and update existing Container Apps in Azure with the latest code. In particular, azure-build and azure-push are the key steps to build and deploy the latest code.

I've done this work and it doesn't look the same...
- azure-login azure-build azure-acr-login-auto azure-push make azure-config-update make azure-fix-client-admin

> client and api containers are going to stay old (new image but containers still started with old ones) [slack [https://w1740803485-clv347541.slack.com/archives/C08F7JZPD63/p](https://w1740803485-clv347541.slack.com/archives/C08F7JZPD63/p) 1743429312766069?thread_ts=1743427320.122109&cid=C08F7JZPD63]
- I see

:

```
az containerapp update --name api --resource-group nishio-kouchou-ai-rg --min-replicas 0 && \
     echo '>>> Re-scaling up again...' && \cH0000000000}
     sleep 5 && \
     az containerapp update --name client-admin --resource-group nishio-kouchou-ai-rg --min-replicas 1
```


2025-04-01
Report has been lost and will be restored.
There seems to be no way to send files to the container, so curl from inside the container in Dropbox.

Entering the Container
`$ az containerapp exec --name api --resource-group nishio-kouchou-ai-rg --command bash`
`$ curl -L "https://www.dropbox.com/s/xxxxx/outputs.zip?dl=1" -o outputs.zip`
`$ apt-get install unzip`
(something) turned out all right



---
This page is auto-translated from [/nishio/p広聴AI2025-03-31~](https://scrapbox.io/nishio/p広聴AI2025-03-31~) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.