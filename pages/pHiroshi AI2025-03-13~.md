---
title: "pHiroshi AI2025-03-13~"
---

[[NEXT_PUBLIC_]]

<img src='https://scrapbox.io/api/pages/nishio-en/o1 Pro/icon' alt='o1 Pro.icon' height="19.5"/>
The following content can be summarized as knowledge that can be easily reused: 1.
1.### Model Deployment for Azure OpenAI Service
.
    - You must specify a specific version number (e.g., `2024-11-20`) in `--model-version`.
        - Specify `--sku` as `Standard` or `GlobalStandard`, and manage throughput with `--capacity` and so on.
    - Similarly for Embedding models, `latest` cannot be used, but the correct version number (e.g. `1`).

2.### Docker architecture issues
.
    - When building on Apple Silicon (M1/M2), etc., you need to specify the platform for x86_64 running on Azure like `docker buildx build --platform linux/amd64 ... ` for x86_64 running on Azure.

3.### Key Vault and App Permissions Settings
.
    - When referencing Key Vault secrets in a Web App, a "Managed ID" must be assigned to the Web App, and the `Key Vault Secrets User` or `Key Vault Secrets Officer` role in Key Vault must be assigned to that ID.
        - Enable the managed ID with `az webapp identity assign` -> grant a role to the said ID with `az role assignment create` -> set `@Microsoft.KeyVault(SecretUri=...) in the Web App's App Settings ` will deploy the secret (however, there are cases where this is not immediately reflected due to lack of privileges, waiting time for role assignment, etc.).

4.### Azure CLI execution notes
.
    - When the default app (Caller appid) in the CLI does not have the authority for Key Vault operations, an additional role assignment is required.
    - When creating resources or setting up Key Vault, JSON output can be saved to a file for later reference for easier management.

5.### Select App Service Plan or SKU
.
    - Basic plans such as B1 are easy for development and testing purposes.
    - The appropriate choice must be made based on load (standard and higher plans are also options).

6.### Deployment Procedure for Multiple Web Apps
.
    - Create Web Apps for different purposes, such as server, client, and management, and deploy containers.
    - Authentication information (e.g., BASIC authentication) can be stored in the Key Vault and referenced as environment variables for easy management.

These are the generic points for deploying and operating AI services and web apps on Azure.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
Well, I'm going to change my policy to do it without Key Vault for once, since I'm getting into trouble with Key Vault related issues and it's not working out well.

> Please check that the image tag matches the image tag that your web app is referencing.
I'm an amateur and I make these kinds of mistakes.

Problem with console.log on server side not being logged
- It was a case of not deploying the console.log that was added in the first place.
- Another story
    - > Please check if "Diagnostic Log" and "Application Log (File System)" are enabled in Azure Portal and if the log level is sufficient.

2025-03-17
[ver.1](https://gist.github.com/nishio/496071fe7c1347ff7f25a10826d31db9) [ver.2](https://gist.github.com/nishio/bd2e30d604c3dad4b8aafe620fbf3635)
[Wide Hearing AI (Digital Democracy 2030) Simplified Azure Deployment Guide](https://gist.github.com/nishio/605f0a9d134f7b33ba1d7a71072bcd85) (ver. 3)

I'll try erasing everything and starting over.

`$ az login`
There's a list of subscriptions among the tenants.
I'm fine with the defaults, so I'll proceed as is.

Creating Resource Groups
Creating Azure OpenAI Service resources
> An existing resource with ID '...kouchou-ai-openai' has been soft-deleted. To restore the resource, you must specify 'restore' to be 'true' in the property. If you don't want to restore existing resource, please purge it first.
You're too kind.
`$ az cognitiveservices account purge --location japaneast --name kouchou-ai-openai --resource-group kouchou-ai-rg --subscription ...`

Model Deployment
Can't this be done through the CLI?
> Go to the Azure OpenAI Service resource you created.
![image](https://gyazo.com/bf7dd6b33c799a499866c69c0e790cd5/thumb/1000)

You say open Azure OpenAI Studio, but I'm not sure if Azure AI Foundry is the way to go.
<img src='https://scrapbox.io/api/pages/nishio-en/o3-mini-high/icon' alt='o3-mini-high.icon' height="19.5"/>
Azure OpenAI Studio, formerly a separate portal, is now integrated into the Azure AI Foundry portal.
So, even if you are instructed to "Open Azure OpenAI Studio", the same functionality is available in the Azure AI Foundry portal, so basically you are fine with Azure AI Foundry.

![image](https://gyazo.com/49d83f8de9c17d6c126647a035da970d/thumb/1000)
![image](https://gyazo.com/5d6ba13f6ded5415337f3c5346f7f410/thumb/1000)

![image](https://gyazo.com/bb80ede6aa81bc37f1edbea239f0f0d9/thumb/1000)
I think the last time I did this was with the CLI.
- I guess I was recommended to go through the web because I was having trouble with a lot of parameters.

Last time I worked on it, the endpoint was `https://kouchou-ai-openai.openai.azure.com`.
The endpoint I got from the above command is `https://japaneast.api.cognitive.microsoft.com/`, something is wrong.
You're right about the former.

Regarding writing the same endpoints in .env
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Can I specify the same endpoint for embedding and gpt4o? How do you differentiate between the requests?
<img src='https://scrapbox.io/api/pages/nishio-en/o3-mini-high/icon' alt='o3-mini-high.icon' height="19.5"/>The same endpoints can be used.
The [[Azure OpenAI Service]] manages multiple deployments with a single endpoint, and distinguishes which model (gpt4o or embedding) to call by specifying a "deploy name" at request time.


[Setting up the Azure App Service
Create App Service Plan

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I'll set up three App Services, what will the cost be, triple?
<img src='https://scrapbox.io/api/pages/nishio-en/o3-mini-high/icon' alt='o3-mini-high.icon' height="19.5"/>App Service fees are charged per App Service Plan, not per individual app.
In other words, placing three apps within the same plan will not necessarily triple the cost. However, if each app is launched on a separate plan, the cost may be higher.
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>In AWS, is it like having three containers running in one EC2?
<img src='https://scrapbox.io/api/pages/nishio-en/o3-mini-high/icon' alt='o3-mini-high.icon' height="19.5"/>Yes, that is correct.
Placing them within the same App Service Plan is like running multiple containers on a single EC2, sharing resources, so costs do not increase unless separate plans are used.

Deployment of Server Components
I'm going to do three in parallel because there's a build wait from here.
> Clone Repository
This is an old name here and needs to be fixed.

`$ docker buildx build --platform linux/amd64 -t kouchou-ai-server:latest ./server`

> Run and test the built Docker image locally

I didn't see this in the last manual, which was kind of nice.
> WARNING: The requested image's platform (linux/amd64) does not match the detected host platform (linux/arm64/v8) and no specific platform was requested
That's right.
> pydantic_core._pydantic_core.ValidationError: 2 validation errors for Settings
>  ADMIN_API_KEY
>  PUBLIC_API_KEY
That's right.
This test is counterproductive w

Saving and Uploading Docker Images

:

```
# Save Docker image to tar file
docker save kouchou-ai-server:latest -o kouchou-ai-server.tar

# gzip the tar file
gzip kouchou-ai-server.tar
```

I can't do docker push without Azure Container Registry...


Deploy to Azure App Service
:

```
# Deploy Docker image
az webapp config container set \
  --resource-group kouchou-ai-rg \
  --name kouchou-ai-server \
  --multicontainer-config-type compose \
  --multicontainer-config-file docker-compose.yml
```

You're talking about something like creating a new docker-compose.yml, but it's not.
What did he say last time?
[https://gist.github.com/nishio/bd2e30d604c3dad4b8aafe620fbf3635#2-web-appの作成サーバー用](https://gist.github.com/nishio/bd2e30d604c3dad4b8aafe620fbf3635#2-web-appの作成サーバー用)
:

```
# Create Web App for server
az webapp create \
  --resource-group kouchou-ai-rg \
  --plan kouchou-ai-plan \
  --name kouchou-ai-server \
  --deployment-container-image-name kouchouaiacr.azurecr.io/server:latest
```

In the first place, last time I checked, you were building the Azure Container Registry.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I already have compose.yaml like when I start up locally, is that ok?
<img src='https://scrapbox.io/api/pages/nishio-en/o3-mini-high/icon' alt='o3-mini-high.icon' height="19.5"/>Basically, you can use compose.yaml for local use. However, when operating with Azure App Service, please check the following points:
- filename: Azure usually recognizes this as "docker-compose.yml", so rename it if necessary.
- Environment variables and port settings: It is necessary to check that the appropriate settings are reflected for the production environment.
It can be used as is if adjusted accordingly.
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>That's not what I did in the last manual, but I wonder if this was done for simplicity's sake.
<img src='https://scrapbox.io/api/pages/nishio-en/o3-mini-high/icon' alt='o3-mini-high.icon' height="19.5"/>That's right. Previously, you may have had to configure each individual setting separately, but this time, docker-compose is designed to centralize the configuration and make it simple to operate.

I wonder if it's true. Well, okay.

Second opinion on the need for RENAME
<img src='https://scrapbox.io/api/pages/nishio-en/o3-mini-high/icon' alt='o3-mini-high.icon' height="19.5"/>By default, the file name is recognized as "docker-compose.yml", so it is safe to rename it if you use "compose.yaml" locally.
If you must use "compose.yaml", you must specify the file name explicitly in the Azure CLI options (e.g., --multicontainer-config-file).

If that's how you feel, I'll specify it explicitly so you don't have to RENAME it.
:

```
# Deploy Docker image
az webapp config container set \
  --resource-group kouchou-ai-rg \
  --name kouchou-ai-server \
  --multicontainer-config-type compose \
  --multicontainer-config-file compose.yaml
```


<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I don't think this CLI side procedure has a timing for uploading IMAGE.
<img src='https://scrapbox.io/api/pages/nishio-en/o3-mini-high/icon' alt='o3-mini-high.icon' height="19.5"/>The CLI procedure does not upload (push) the Docker image itself.
Typically, images are pushed in advance to an external registry, such as Docker Hub or Azure Container Registry, and the CLI is used to configure the App Service by referencing images on that registry.
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Instance of Azure Container Registry this time? I didn't create it.
<img src='https://scrapbox.io/api/pages/nishio-en/o3-mini-high/icon' alt='o3-mini-high.icon' height="19.5"/>Yes. This guide is focused on simple configuration and uses a direct upload of locally built and stored Docker images without the use of ACR.
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Can I upload via CLI? Can I only do it from a browser?
<img src='https://scrapbox.io/api/pages/nishio-en/o3-mini-high/icon' alt='o3-mini-high.icon' height="19.5"/>
The CLI basically does not provide the ability to upload local Docker image files directly.
Typically, you push an image to a container registry (such as ACR or Docker Hub) and reference that image from the App Service, or upload a local image using the Deployment Center in your browser.


Ugh, what a pain in the ass...maybe I should include it since ACR creation isn't that much of a snag.

![image](https://gyazo.com/96583ca24af835e4d49b4051b38ab334/thumb/1000)
It's recommended to plug in GitHub Actions.
So that's it, I'm doing docker buildx at hand now, but in the future I should do it with GitHub Actions?

![image](https://gyazo.com/39ab4e6e9c2904e67be0dccd2a5e486f/thumb/1000)
No, if I build with GitHub Actions, that just means I end up pushing to ACR or Docker Hub and then pull with that trigger. I'd rather set up ACR then.

<img src='https://scrapbox.io/api/pages/nishio-en/o3-mini-high/icon' alt='o3-mini-high.icon' height="19.5"/>
Since local files cannot be uploaded directly to Azure App Service, Docker images are generally pushed to ACR (Azure Container Registry) for use.
Here are the simple steps

1.### Create ACR
.
- `$ az acr create --resource-group kouchou-ai-rg --name aikouchouacr --sku Basic`

2.### Log in to ACR
.
- `$ az acr login --name aikouchouacr`

3.### Build and tag Docker images
.
- `$ docker buildx build --platform linux/amd64 -t kouchou-ai-server:latest ./server`

- `$ docker tag kouchou-ai-server:latest aikouchouacr.azurecr.io/kouchou-ai-server:latest`

4.### push to ACR
.
- `$ docker push aikouchouacr.azurecr.io/kouchou-ai-server:latest`

5.### App Service Settings
.
- In Azure Portal's "Container Settings", select ACR as the source and specify the repository name and tags.

This will allow you to retrieve images from the ACR and run containers in the App Service.

`$ az acr update -n aikouchouacr --admin-enabled true`
`$ az acr credential show --name aikouchouacr --resource-group kouchou-ai-rg`

:

```
az webapp config container set \
  --resource-group kouchou-ai-rg \
  --name kouchou-ai-server \
  --docker-custom-image-name aikouchouacr.azurecr.io/kouchou-ai-server:latest \
  --docker-registry-server-url https://aikouchouacr.azurecr.io \
  --docker-registry-server-user <ACR username> \
  --docker-registry-server-password <ACR password>.
```


Reboot
`$ az webapp restart --resource-group kouchou-ai-rg --name kouchou-ai-server`

Let's look at the log to see if the server has started.
:

```
# Check App Service logs
az webapp log tail \
  --resource-group kouchou-ai-rg \
  --name kouchou-ai-server
```


I don't see the log.

-----

`% # Log in to ACR`
az acr login --name kouchouaiacr
zsh: command not found: #
Could not connect to the registry login server 'kouchouaiacr.azurecr.io'. Please verify that the registry exists and the URL '[https://kouchouaiacr.azurecr.io/v2/'](https://kouchouaiacr.azurecr.io/v2/') is reachable from your environment.
Try running 'az acr check-health -n kouchouaiacr --yes' to diagnose this issue.

- `% az acr check-health -n kouchouaiacr --yes`
Docker daemon status: available
Docker version: 'Docker version 20.10.22, build 42c8b31, platform linux/arm64'
Docker pull of 'mcr.microsoft.com/mcr/hello-world:latest' : OK
Azure CLI version: 2.70.0
2025-03-17 08:23:50.591717 An error occurred: CONNECTIVITY_DNS_ERROR
Failed to reach DNS for registry 'kouchouaiacr.azurecr.io'. Please check if the spelling is correct, if the CLI environment is on correct cloud and your network connectivity.

Two ACRs cause login failures? Unexplained

---
<img src='https://scrapbox.io/api/pages/nishio-en/o3-mini-high/icon' alt='o3-mini-high.icon' height="19.5"/>
In the Azure CLI, the
--docker-custom-image-name → --container-image-name
--docker-registry-server-url → --container-registry-url
--docker-registry-server-user → --container-registry-user
--docker-registry-server-password → --container-registry-password
is recommended. Use the new option in the future.

---
No logging issue, rather Azure Portal log stream can connect.
- Sometimes it doesn't connect.

admin

```
2025-03-17T08:52:06  Welcome, you are now connected to log-streaming service.Starting Log Tail -n 10 of existing logs ----/appsvctmp/volatile/logs/runtime/container.log
2025-03-17T08:51:15.3231533Z Configure Services : 08.51.15.322864
2025-03-17T08:51:16.7442581Z Configure : 08.51.16.743970
2025-03-17T08:51:17.6208151Z Setting Up Routes : 08.51.17.620555
2025-03-17T08:51:18.2362864Z Exiting Configure : 08.51.18.236021
2025-03-17T08:51:18.6132403Z [40m[1m[33mwarn[39m[22m[49m: Microsoft.AspNetCore.DataProtection.KeyManagement.XmlKeyManager[35]
2025-03-17T08:51:18.6133451Z       No XML encryptor configured. Key {fdf3c2ce-05ea-4c38-a6ba-9cffe3df9d1b} may be persisted to storage in unencrypted form.
2025-03-17T08:51:18.8348701Z Hosting environment: Production
2025-03-17T08:51:18.8359212Z Content root path: /opt/Kudu
2025-03-17T08:51:18.8533469Z Now listening on: http://0.0.0.0:8181
2025-03-17T08:51:18.8534039Z Application started. Press Ctrl+C to shut down.Ending Log Tail of existing logs ---Starting Live Log Stream ---
2025-03-17T08:53:06  No new trace in the past 1 min(s).
2025-03-17T08:53:50.5848228Z
2025-03-17T08:53:50.7628783Z > kouchou-ai-client-admin@0.1.0 start
2025-03-17T08:53:50.7629743Z > next start -p 4000
2025-03-17T08:53:50.7629784Z
2025-03-17T08:53:54.5458289Z    ▲ Next.js 15.1.6
2025-03-17T08:53:54.5460079Z    - Local:        http://localhost:4000
2025-03-17T08:53:54.5460176Z    - Network:      http://169.254.132.3:4000
2025-03-17T08:53:54.5460215Z
2025-03-17T08:53:54.5460243Z  ✓ Starting...
2025-03-17T08:53:56.3796807Z  ✓ Ready in 3.9s
2025-03-17T08:55:06  No new trace in the past 1 min(s).
```


client

```
2025-03-17T08:48:53  Welcome, you are now connected to log-streaming service.Starting Log Tail -n 10 of existing logs ----/home/LogFiles/__lastCheckTime.txt  (https://kouchou-ai-client.scm.azurewebsites.net/api/vfs/LogFiles/__lastCheckTime.txt)03/17/2025 08:47:13/home/LogFiles/kudu/trace/c2a2216e2cb4-c522ab4a-31c3-44b4-8dae-bd0dd87d61cf.txt  (https://kouchou-ai-client.scm.azurewebsites.net/api/vfs/LogFiles/kudu/trace/c2a2216e2cb4-c522ab4a-31c3-44b4-8dae-bd0dd87d61cf.txt)
2025-03-17T08:48:52  Startup Request, url: /api/logstream/, method: GET, type: request, pid: 776,1,5, ScmType: None/home/LogFiles/2025_03_17_lw1sdlwk000C43_default_docker.log  (https://kouchou-ai-client.scm.azurewebsites.net/api/vfs/LogFiles/2025_03_17_lw1sdlwk000C43_default_docker.log)
2025-03-17T08:44:56.888979144Z
2025-03-17T08:44:56.889594374Z > kouchou-ai-client@0.1.0 build
2025-03-17T08:44:56.889598946Z > next build
2025-03-17T08:44:56.889601478Z
2025-03-17T08:45:09.723432943Z    ??? Next.js 15.1.6
2025-03-17T08:45:09.743210166Z
2025-03-17T08:45:09.834319984Z    Creating an optimized production build .../home/LogFiles/2025_03_17_lw1sdlwk000C43_docker.log  (https://kouchou-ai-client.scm.azurewebsites.net/api/vfs/LogFiles/2025_03_17_lw1sdlwk000C43_docker.log)
2025-03-17T08:46:31.303Z INFO  - Waiting for response to warmup request for container kouchou-ai-client_0_4abf5642. Elapsed time = 100.3545987 sec
2025-03-17T08:46:48.895Z INFO  - Waiting for response to warmup request for container kouchou-ai-client_0_4abf5642. Elapsed time = 117.9464186 sec
2025-03-17T08:47:05.550Z INFO  - Waiting for response to warmup request for container kouchou-ai-client_0_4abf5642. Elapsed time = 134.6007097 sec
2025-03-17T08:47:27.022Z INFO  - Waiting for response to warmup request for container kouchou-ai-client_0_4abf5642. Elapsed time = 156.0733663 sec
2025-03-17T08:47:49.023Z INFO  - Waiting for response to warmup request for container kouchou-ai-client_0_4abf5642. Elapsed time = 178.0737392 sec
2025-03-17T08:48:14.332Z INFO  - Waiting for response to warmup request for container kouchou-ai-client_0_4abf5642. Elapsed time = 203.3826478 sec
2025-03-17T08:48:31.846Z INFO  - Waiting for response to warmup request for container kouchou-ai-client_0_4abf5642. Elapsed time = 220.8968595 sec
2025-03-17T08:48:42.925Z ERROR - Container kouchou-ai-client_0_4abf5642 for site kouchou-ai-client did not start within expected time limit. Elapsed time = 231.948246 sec
2025-03-17T08:48:43.097Z ERROR - Container kouchou-ai-client_0_4abf5642 didn't respond to HTTP pings on port: 3000, failing site start. See container logs for debugging.
2025-03-17T08:48:43.347Z INFO  - Stopping site kouchou-ai-client because it failed during startup.Ending Log Tail of existing logs ---Starting Live Log Stream ---
2025-03-17T08:49:54  No new trace in the past 1 min(s).
```


Server error
![image](https://gyazo.com/1e278d66dc93bac3ceb5864aac73fa8b/thumb/1000)

[https://gist.github.com/nishio/7745a8449c0688976db9aebfb5aa398e](https://gist.github.com/nishio/7745a8449c0688976db9aebfb5aa398e)
<img src='https://scrapbox.io/api/pages/nishio-en/o3-mini-high/icon' alt='o3-mini-high.icon' height="19.5"/>
The logs show that the container is missing configuration information required for startup (in particular, ADMIN_API_KEY, PUBLIC_API_KEY, OPENAI_API_KEY, etc.), resulting in a Pydantic validation error on the application side. As a result, the application is unable to start properly and cannot respond to HTTP pings, resulting in a final startup timeout.

Countermeasures

Setting Required Environment Variables
Set the environment variables (ADMIN_API_KEY, PUBLIC_API_KEY, OPENAI_API_KEY, etc.) that the application requires at startup from "Configuration" > "App Settings" in Azure App Service.

:

```
az webapp config appsettings set \
 --resource-group kouchou-ai-rg \
 --name kouchou-ai-server \
 --settings ADMIN_API_KEY="admin" PUBLIC_API_KEY="public" OPENAI_API_KEY="..."
```


Maybe we should use a validation to make it OK without USE_AZURE.

- [[Make # a comment in zsh]]

I was getting all kinds of errors and stuff, but as I was working on other things, I realized it was done.
[https://gist.github.com/nishio/df0513d9ac5219e848390315d08d03fe](https://gist.github.com/nishio/df0513d9ac5219e848390315d08d03fe)

![image](https://gyazo.com/9ce8d8e5e3545db739919950fde501ef/thumb/1000)
Whoa, looks like processing has begun.

The question is, is the report writing going properly, or is it falling apart behind the scenes due to errors?
Also, client still doesn't show up.

Today's Progress
- Delete the resource group and start over.
- Generate a simple document (ver. 3) for a route that does not use Key Vault and follow it.
- The document did not use Azure Container Registry either, but that would have required a browser operation, which would have been a hassle, so I decided to use ACR and regenerated the document.
- I was able to upload the CSV from the admin screen and start the process. However, it did not complete after a sufficient amount of time, so I think it is dying due to an error on the server side. The cause is unknown, as the error logs that the application produces do not seem to flow into the log stream by default.
- The client still won't start. Maybe it can't communicate through localhost in Azure App Service to connect to server.

2025-03-18
Talking about deploying in Azure environment and using Azure OpenAI Service are independent of each other.
that's true
The repositories have just changed a lot, so let's start from scratch with the whole repository.

[https://github.com/digitaldemocracy2030/kouchou-ai](https://github.com/digitaldemocracy2030/kouchou-ai)
fork
[https://github.com/nishio/kouchou-ai](https://github.com/nishio/kouchou-ai)
clone, put OpenAI API key in .env and docker-compose up

> Attaching to kouchou-ai-api-1, kouchou-ai-client-1, kouchou-ai-client-admin-1
>  Error response from daemon: driver failed programming external connectivity on endpoint kouchou-ai-api-1 (0ad5b0eeabca84ef698349ed3093339034298f7711c03d847781b61a2b7a55d4): Bind for 0.0.0.0:8000 failed: port is already allocated
Oops, somewhere the 8000 number is being used.

[[Where is the port being used?]]
`$ sudo lsof -i :8000`

The old server was still alive, so I killed it and docker up again.

Localhost:4000 will bring up the admin screen.
![image](https://gyazo.com/fbd7a1107e02b39b6c836602b7d0fd51/thumb/1000)
API OKs at localhost:8000.
No client on localhost:3000 but...
Looks like the build just took a long time.
:

```
kouchou-ai-client-1        | 
kouchou-ai-client-1        | > kouchou-ai-client@0.1.0 build
kouchou-ai-client-1        | > next build
kouchou-ai-client-1        | 
kouchou-ai-client-1        |    ▲ Next.js 15.1.6
kouchou-ai-client-1        | 
kouchou-ai-client-1        |    Creating an optimized production build ...
```

...
:

```
kouchou-ai-client-1        |  ✓ Compiled successfully
kouchou-ai-client-1        |    Linting and checking validity of types ...
kouchou-ai-client-1        | 
kouchou-ai-client-1        | ./components/report/ClientContainer.tsx
kouchou-ai-client-1        | 30:6  Warning: React Hook useEffect has a missing dependency: 'fetchReport'. Either include it or remove the dependency array.  react-hooks/exhaustive-deps
kouchou-ai-client-1        | 
kouchou-ai-client-1        | info  - Need to disable some ESLint rules? Learn more here: https://nextjs.org/docs/app/api-reference/config/eslint#disabling-rules
kouchou-ai-client-1        |    Collecting page data ...
kouchou-ai-client-1        |    Generating static pages (0/4) ...
kouchou-ai-client-1        |    Generating static pages (1/4) 
kouchou-ai-client-1        |    Generating static pages (2/4) 
kouchou-ai-client-1        |    Generating static pages (3/4) 
kouchou-ai-client-1        |  ✓ Generating static pages (4/4)
kouchou-ai-client-1        |    Finalizing page optimization ...
kouchou-ai-client-1        |    Collecting build traces ...
kouchou-ai-client-1        | 
kouchou-ai-client-1        | Route (app)                              Size     First Load JS
kouchou-ai-client-1        | ┌ ○ /                                    2.3 kB          152 kB
kouchou-ai-client-1        | ├ ○ /_not-found                          986 B           107 kB
kouchou-ai-client-1        | └ ● /[slug]                              33.1 kB         183 kB
kouchou-ai-client-1        | + First Load JS shared by all            106 kB
kouchou-ai-client-1        |   ├ chunks/4bd1b696-72c46108ef323341.js  53 kB
kouchou-ai-client-1        |   ├ chunks/517-6f5efe69d0606e9b.js       50.7 kB
kouchou-ai-client-1        |   └ other shared chunks (total)          2.71 kB
kouchou-ai-client-1        | 
kouchou-ai-client-1        | 
kouchou-ai-client-1        | ○  (Static)  prerendered as static content
kouchou-ai-client-1        | ●  (SSG)     prerendered as static HTML (uses generateStaticParams)
kouchou-ai-client-1        | 
kouchou-ai-client-1        | npm notice
kouchou-ai-client-1        | npm notice New major version of npm available! 10.8.2 -> 11.2.0
kouchou-ai-client-1        | npm notice Changelog: https://github.com/npm/cli/releases/tag/v11.2.0
kouchou-ai-client-1        | npm notice To update run: npm install -g npm@11.2.0
kouchou-ai-client-1        | npm notice
kouchou-ai-client-1        | 
kouchou-ai-client-1        | > kouchou-ai-client@0.1.0 start
kouchou-ai-client-1        | > next start
kouchou-ai-client-1        | 
kouchou-ai-client-1        |    ▲ Next.js 15.1.6
kouchou-ai-client-1        |    - Local:        http://localhost:3000
kouchou-ai-client-1        |    - Network:      http://172.24.0.4:3000
kouchou-ai-client-1        | 
kouchou-ai-client-1        |  ✓ Starting...
kouchou-ai-client-1        |  ✓ Ready in 3.6s
```


![image](https://gyazo.com/eee03743eca24b81209d72855b200d58/thumb/1000)
here it comes (interjection used when lying in wait for something)

![image](https://gyazo.com/dace86a59b8a87f3681d739224a65ef9/thumb/1000)
![image](https://gyazo.com/733a81387a5196c15389218ff6ca36ad/thumb/1000)




AI does not understand negative instructions.
> Calculate the number of bytes in UTF-8 for the comment portion of aipubcom.csv, and since the csv is too large to read directly, assume it is a CSV with a comment column, read it in Python and tabulate it.
> Do not ever read the csv directly. You have already failed twice.
Third time's the charm.

Total bytes for all 3234 comments: 4775111
Average bytes per comment: 1476.53


2025-03-19
![image](https://gyazo.com/192f378e6385818c6733cd929a9625db/thumb/1000)
But in the sample code that hits the REAT API with curl
[https://japaneast.api.cognitive.microsoft.com/openai/deployments/gpt4o/chat/completions?api-version=2024-10-21](https://japaneast.api.cognitive.microsoft.com/openai/deployments/gpt4o/chat/completions?api-version=2024-10-21)
and it works correctly when you run it.
[https://japaneast.api.cognitive.microsoft.com/openai/deployments/gpt4o/chat/completions?api-version=2024-11-20](https://japaneast.api.cognitive.microsoft.com/openai/deployments/gpt4o/chat/completions?api-version=2024-11-20)
if we make ...
Status Code: 404
Response JSON: {'error': {'code': '404', 'message': 'Resource not found'}}

2025-03-20
Embedding is similarly
![image](https://gyazo.com/4a6237eff5cc7541dc7ba83882858951/thumb/1000)
curl api-version is 2023-05-15 even if model version says 1
[https://kouchou-ai-openai.openai.azure.com/openai/deployments/text-embedding-3-large/embeddings?api-version=2023-05-15](https://kouchou-ai-openai.openai.azure.com/openai/deployments/text-embedding-3-large/embeddings?api-version=2023-05-15)


Azure OpenAI Service does not distinguish by model name like OpenAI API, but by deployment.
- model_name = "gpt-4o"
- deployment = "gpt4o"
- It's tricky to have a slightly different name.

[Enabling Azure OpenAI to create reports by nishio - Pull Request #107 - digitaldemocracy2030/kouchou-ai [https://github.com/digitaldemocracy2030/kouchou-](https://github.com/digitaldemocracy2030/kouchou-) ai/pull/107]

2025-03-21
[Make it easy to set up in an Azure environment by shingo-ohki - Pull Request #115 - digitaldemocracy2030/kouchou-ai [https://github.com/digitaldemocracy2030/](https://github.com/digitaldemocracy2030/) kouchou-ai/pull/115]
`$ git remote add truego https://github.com/shingo-ohki/kouchou-ai.git`
`$ git fetch truego feature/deploy-Azure`
`$ git checkout -b feature/deploy-Azure truego/feature/deploy-Azure`

Replace all ACR names
Set docker build to `buildx build --platform linux/amd64

`$ make azure-build`
`$ make azure-push`
- If you don't do $ make azure-acr-login-auto first
`$ make azure-deploy`
what is he doing?
<img src='https://scrapbox.io/api/pages/nishio-en/Devin/icon' alt='Devin.icon' height="19.5"/>
This section details the contents of azure-deploy. This command performs the following critical steps

1. configure extensions and providers for Container Apps
:

```
az extension add --name containerapp --upgrade
az provider register --namespace Microsoft.App
az provider register --namespace Microsoft.OperationalInsights --wait
```


These are the basic settings required to use Azure Container Apps.

Create Log Analytics workspace
:

```
az monitor log-analytics workspace create \
-resource-group kouchou-ai-rg \
 -workspace-name kouchou-ai-logs \
 -location japaneast
```


This workspace is used to collect and analyze container logs.

Creation of Container Apps environment
:

```
az containerapp env create \
-name kouchou-ai-env \
 -resource-group kouchou-ai-rg \
 -location japaneast \
 -logs-workspace-id $WORKSPACE_ID
```


This sets up a shared environment for running the three container apps.

4. activation of administrative access rights for ACR
:

```
az acr update \
-name kouchouairegistry \
 -resource-group kouchou-ai-rg \
 -admin-enabled true
```


This allows Container Apps to pull images from the ACR.

5. deploy each container app
- API Container (Port 8000)
- Client container (port 3000)
- Admin client container (port 4000)

Each container is created with the following settings
- Accessible to the outside (ingress external)
- Minimum number of replicas1
- Use ACR credentials
- Appropriate port settings

This command deploys the three components of the broadband AI into a fully configured Azure environment.

2025-03-25
az containerapp exec \
    - --name <container app name> \c
    - --resource-group <resource group name> }
    - --container <container name> \cHTML
    - --command "/bin/bash"

[https://app.devin.ai/sessions/895b427620ef45c79a992efb319d31ac✅](https://app.devin.ai/sessions/895b427620ef45c79a992efb319d31ac✅)

2025-03-27
- [[Salvage from a widely-heard AI]]
az containerapp exec --name api --resource-group nishio-kouchou-ai-rg --container api --command "/bin/bash"


---
This page is auto-translated from [/nishio/p広聴AI2025-03-13~](https://scrapbox.io/nishio/p広聴AI2025-03-13~) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.